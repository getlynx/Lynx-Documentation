---
description: >-
  Use this method to store payloads that are 2,000 bytes (2KB) or greater. If
  your payload is consistently under this threshold, then please use the Data
  method.
cover: >-
  https://get.clevver.org/1c501e05d2a252a28b46fa7971e0b5b4782e16f1ebcceb20dd28701f74cce197.png
coverY: 0
---

# Span Payload

{% swagger baseUrl="https://api.logware.io" path="/api/span" method="post" summary="StoreSpan" %}
{% swagger-description %}
Post the Span value you wish to store, get a response with a Task Id. Use the Get method with the Task Id to get the Transaction Id. The Task Id can be discarded. The Transaction Id is permanent. Store the Transaction Id for future lookup of the Span value stored.
{% endswagger-description %}

{% swagger-parameter in="header" name="token" type="string" %}
Authentication Bearer Token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="env" type="string" %}
Target environment [ prod | test ]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="span" type="string" %}
The Span string to store
{% endswagger-parameter %}

{% swagger-response status="201" description="The Task Id is created and is the only value in the response package. Below is a sample of the response." %}
```
44ef3487-4877-424f-9f9f-f6df42876f72
```
{% endswagger-response %}
{% endswagger %}

The Task Id included in the StoreSpan method response is temporary and does not need to be saved long term. Use the Task Id to get the Transaction Id with the StoreSpanId method below. The Transaction Id is permanent and must be saved if you intend to look up the data value stored later in the future. After 1 hour, the Task Id is expunged and no longer accessible.

{% swagger baseUrl="https://api.logware.io" path="/api/span/[env]/[taskid]" method="get" summary="StoreSpanId" %}
{% swagger-description %}
The Transaction Id will be available within 5 seconds of the StoreSpan POST method response. Use this method to get the permanent Transaction Id of the stored Span value. Your application has 1 hour to get the Transaction Id. After 1 hour passes, the Task Id gets expunged. If you miss the 1 hour expiry, you will need to store another record to get a new Transaction Id.
{% endswagger-description %}

{% swagger-parameter in="header" name="token" type="string" %}
Authentication Bearer Token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="env" type="string" %}
Target environment [ prod | test ]
{% endswagger-parameter %}

{% swagger-parameter in="query" name="taskid" type="string" %}
The value provided in the StoreSpan POST response
{% endswagger-parameter %}

{% swagger-response status="200" description="The following response contains the Transaction Id value inside the Content key. This is  the primary data of interest and should be saved for future lookups." %}
```
{
    "LTaskId": "44ef3487-4877-424f-9f9f-f6df42876f72",
    "ReponseCode": 200,
    "Content": [
        "85b07457aa23d4e0e394af0dd16368e42ffc10b04fde8ccb56883c3bb684b4ca"
    ]
}
```
{% endswagger-response %}

{% swagger-response status="404" description="If you search for a Task Id that has expired or does not exist, you will get a response like this." %}
```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "|b760a5ce-4728838d6c943826."
}
```
{% endswagger-response %}
{% endswagger %}
