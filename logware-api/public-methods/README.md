---
description: The following instructions should get your initial API test working quickly.
cover: >-
  https://get.clevver.org/4e4c669f2986adc25766967d2bb70a8d737face1616a94b7f93154025fe7d113.png
coverY: 0
---

# Public Methods

Logware customers are encouraged to silo API keys for application-specific usage. This recommendation reinforces a security model that allows an application-specific key to be easily deactivated without impacting correlative services in the client stack.

## Authenticate first

Before you select the Payload type you will be working with; you must authenticate with your API credentials. Once your application gets a Token, it's usable for 10 hours.&#x20;

{% hint style="info" %}
Your application should re-authenticate every 10 hours, no sooner.
{% endhint %}

## Upload your Payload

We recommend a single API key for each type of payload you store in your application. For the sake of getting started fast, try the Hash Payload method first.

{% hint style="info" %}
Code snippets for various clients are also provided in [API Samples](https://docs.getlynx.io/logware-api/api-snippets) section of this documentation.
{% endhint %}
