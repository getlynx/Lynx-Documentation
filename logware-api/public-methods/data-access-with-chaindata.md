---
description: >-
  Retrieval from ChainData allows the developer to skip using the API and
  instead, directly access the CDN.
cover: >-
  https://get.clevver.org/acdbfd2252282562e203a467b4831c07d0f301fa1f6f02534251b3a3c53da7f8.png
coverY: 0
---

# Reading from ChainData

During client implementations, the developers of Logware realized that an intermediary content delivery network (CDN) layer would be of great value to customers looking to quickly and visually gain access to past payloads stored.

{% hint style="success" %}
The [Payload Explorer](https://explorer.logware.io/) site allows for a manual search and inspection of a record by a human, much like a traditional blockchain explorer website.
{% endhint %}

But your application can also search for a Transaction Id without using the API. The positive impact is that even if your API key has expired or was disabled, your applications can still gain access to your data without restriction.

The ChainData is a unique website resulting from an indexing service run by Lynx that downloads into an Amazon Web Service (AWS) CloudFront CDN a full copy of all blockchain content. Thus, enabling quick searches of payload data without charge. There is a very short delay between the time that content gets stored in the blockchain and when it becomes available in the ChainData set, but once it's there, it's there forever.

{% hint style="warning" %}
A 10-minute delay from the time a block gets created on the Lynx network and the data showing up in the ChainData CDN can be expected.
{% endhint %}
