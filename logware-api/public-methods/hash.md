---
description: >-
  Use this method to store SHA256 hash strings. Ideal hash length is 64
  characters with no spaces or special characters.
cover: >-
  https://get.clevver.org/4d415763db37c7fd22aaf380d9262c4c59f6cf633834f3cde1257988049578ab.png
coverY: 0
---

# Hash Payload

{% swagger baseUrl="https://api.logware.io" path="/api/hash" method="post" summary="StoreHash" %}
{% swagger-description %}
Post the Hash value you wish to store, get a response with a Task Id. Use the Get method with the Task Id to get Transaction Id. The Task Id can be discarded. The Transaction Id is permanent. Store the Transaction Id for future lookup of the Hash value stored.
{% endswagger-description %}

{% swagger-parameter in="header" name="token" type="string" %}
Authentication Bearer Token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="env" type="string" %}
Target environment [ prod | test ]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="hash" type="string" %}
The hash string to store
{% endswagger-parameter %}

{% swagger-response status="201" description="The Task Id is created and is the only value in the response package. Below is a sample of the response." %}
```
5d911d6f-a192-4a45-a57f-e7a0946676e4
```
{% endswagger-response %}

{% swagger-response status="404" description="Could not find a cake matching this query." %}
```
{    "message": "Ain't no cake like that."}
```
{% endswagger-response %}
{% endswagger %}

The Task Id included in the StoreHash method response is temporary and does not need to be saved. Use the Task Id to get the Transaction Id with the StoreHashId method below. The Transaction Id is permanent and must be saved if you intend to look up the hash value stored later in the future. After 1 hour, the Task Id is expunged and no longer accessible.

{% swagger baseUrl="https://api.logware.io" path="/api/hash/[env]/[taskId]" method="get" summary="StoreHashId" %}
{% swagger-description %}
The Transaction Id will be available within 5 seconds of the StoreHash POST method response. Use this method to get the permanent Transaction Id of the stored Hash value. Your application has 1 hour to get the Transaction Id. After 1 hour passes, the Task Id is expunged. If you miss the 1 hour expiry, you will need to store another record to get a new Transaction Id.
{% endswagger-description %}

{% swagger-parameter in="header" name="token" type="string" %}
Authentication Bearer Token
{% endswagger-parameter %}

{% swagger-response status="200" description="The value in the Content key is of primary interest. It is split into two halves. The first half contains the original hash value stored and the second have contains the Transaction Id. The Transaction Id should be saved for future lookups." %}
```
{
    "LTaskId": "5d911d6f-a192-4a45-a57f-e7a0946676e4",
    "ReponseCode": 200,
    "Content": [
        "bdbc0d772d613f2f37f9a4988cd5bb0c59995cb7467bb0f2ea3cf000540f7fa9::2e7bf06e33e04bd43500da9fe66dcd26a61539558df1451fc849af7ac08c931a"
    ]
}
```
{% endswagger-response %}

{% swagger-response status="404" description="If the Task Id has expired or is no longer available, you will receive a response like the one below. " %}
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "|64709a6a-46418e07eb8ba31a."
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://api.logware.io" path="/api/hash/retrieve" method="post" summary="RetrieveHash" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="token" type="string" %}
Authentication Bearer Token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="env" type="string" %}
Target environment [ prod | test ]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txid" type="string" %}
The Transaction Id of the hash you wish to retrieve.
{% endswagger-parameter %}

{% swagger-response status="201" description="A TaskId is created and is the only value in the response package. Below is a sample of the Task Id." %}
```
56c1e9fd-ee6a-472d-be7a-1b332fe4c9a2
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://api.logware.io" path="/api/hash/retrieve/[env]/[taskId]" method="get" summary="RetrieveHashId" %}
{% swagger-description %}
The hash value stored will be retrieved with the correct environment and taskId value supplied in the url query parameter. 
{% endswagger-description %}

{% swagger-parameter in="path" name="token" type="string" %}
Authentication Bearer Token
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "LTaskId": "13dce337-8385-4b90-b750-7d92e6cfcca3",
    "ReponseCode": 200,
    "Content": [
        "5c35811dc04090665b5c8c79d6756ed2e3e924dfefff99ddd01d8c314e163a5f::bdbc0d772d613f2f37f9a4988cd5bb0c59995cb7467bb0f2ea3cf000540f7fa9"
    ]
}
```
{% endswagger-response %}

{% swagger-response status="400" description="" %}
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "|b760aaf5-4728838d6c943826."
}
```
{% endswagger-response %}
{% endswagger %}
