---
description: >-
  An authentication token is required prior to interacting with any of the three
  payload types.
cover: >-
  https://get.clevver.org/46ce394527720b776c0a2227736d126c3ebd15b4d158ef344237cbf5a62837dc.png
coverY: 0
---

# Authentication

Logware’s API uses JSON Web Token (JWT) authentication. Any endpoints that require authorization will need this token to be included in an “Authorization Bearer” header. Once generated, a token is valid for 10 hours. You can regenerate a new token at any time.

{% swagger baseUrl="https://api.logware.io" path="/api/users/authenticate" method="post" summary="Authenticate" %}
{% swagger-description %}
This authentication method is only needed once every 10 hours. Please track the age of the token so the application is not requesting a new token before each StoreHash, StoreData, or StoreSpan method invocation.
{% endswagger-description %}

{% swagger-parameter in="header" name="content-type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="login" type="string" %}
Login assigned by Logware Sales
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
Password assigned by Logware Sales
{% endswagger-parameter %}

{% swagger-response status="200" description="Authentication token successfully retrieved." %}
```
{
    "login": "my-API-login",
    "password": null,
    "token": "eyJhbGciOiJIUzI1KiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9zaWQiOiI5N2NjYzUyZC1jNWE1LWNlMTItMmM5Mi02MDE5ODJhYjYyM2YiLCJ1bmlxdWVfbmFtZSI6IkFlZ2lzLVN0YWdpbmciLCJodHRwOi8vc2NoZW1hcy5taWNyb3NvZnQuY29tL3dzLzIwMDgvMDYvaWRlbnRpdHkvY2xhaW1zL3VzZXJkYXRhIjoiP0JwRUFvPD85QEJtbzlDbUBvOUBxPkI5QXBuRG0-QW9vb29wOEA-cEBBQUBCOUVtbz85QEJFbTlEcEQ9OUFwbkRtPkNAbnJFbThAQ0BDPUVxPzlEcjxuOW1AQXE5PDxDcTlBcG5EbT5tPnJCRTw4RG9uPEREQEU5cT9AcjltPURuOT5yQUI5QXBuRG0-ckFxQXBAOG49bz9DQG1xOXJvRXE5RT5ERTlycG9uOUFwbkRtPkFyb29FRThvRUJBRUFFbTk9QTxCOXE_PT45PkRDPjlBcG5EbT4-Qm4-QXA4wog-RUFERG9tbTk8bkNvOUE8RW05cXBCcjlBcG5FPEREbnJub204P3BCP0RFckQ5bT9BcjlEbm9COUQ9PEM5QXBuRTxEPj5yP3A8OCIsIm5iZiI6MTYzMzY1NTc0MywiZXhwIjoxNjMzNjk4OTQzLCJpYXQiOjE2MzM2NTU3NDN9.Du9ZaCwL4Yc-9ru96V1kajTPmZAEj_CB08pBtW6OUvk",
    "id": "97ccc52d-c5a4-ce12-2c92-601982ab623f"
}
```
{% endswagger-response %}

{% swagger-response status="400" description="" %}
```
{ "message": "Username or password incorrect" }
```
{% endswagger-response %}
{% endswagger %}

{% hint style="success" %}
Within a 200 Response, the token value is the primary interest. All other values can be discarded.
{% endhint %}
