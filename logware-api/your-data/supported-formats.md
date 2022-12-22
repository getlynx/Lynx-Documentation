---
cover: >-
  https://get.clevver.org/2a42830821dd55e7ebc4d3f14317b9b0235062a98840513d8c4f106e5d8c90d1.png
coverY: -244.60431654676256
---

# Supported Formats

There are no restrictions about the formats or data types your application can use with the API. However, customers often choose to encrypt their data, so the complexity of data-type selection gets obfuscated from the API layer. Even binary data can be encoded and then encrypted.

{% hint style="info" %}
Developers are encouraged to encode plaintext content in base64. Encoding resolves a difficulty with special characters and escapes conflicts with single and double-quote characters in the payload content.
{% endhint %}

This [website provides](https://base64.guru/converter/encode) an easy-to-use testing environment for manually encoding and decoding content.
