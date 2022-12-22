---
cover: >-
  https://get.clevver.org/2a42830821dd55e7ebc4d3f14317b9b0235062a98840513d8c4f106e5d8c90d1.png
coverY: 0
---

# Cloud Farms

In our experience, Amazon Web Services (AWS) is the _most expensive vendor_ to use for a cloud-based Lynx Farm because they penalize you for high CPU usage.

Therefore, if you build a Lynx Farm in the cloud, we recommend alternative cloud vendors like [Linode](https://www.linode.com/), [Digital Ocean](https://www.digitalocean.com/), and [Scaleway](https://www.scaleway.com/en/). In the case of these vendors, the 2GB RAM/1 CPU configuration is best. Lynx requires no less than 1GB of RAM to run. You will probably need +2GB of SWAP on those VPS, so keep that mind. The LynxCI installer will configure your SWAP allocation for you automatically. Having a node with 2GB of RAM is IDEAL, but that takes the price to USD 10/m for each node. If you are running a Farm, your goal is to create as many small nodes as possible. The Lynx daemon wants as many CPU core threads as it can get. If a node has one core per CPU, then Lynx will only mine on one thread. If you have a VPS with four cores, Lynx will mine with four unique threads. Lynx handles thread management for you. It would be best if you were looking to get as many cores as you can with your target VPS.&#x20;

{% hint style="info" %}
Some eBay sellers list off-lease corporate desktop computers very inexpensively, and these are ideal computers to build Lynx Farms as well.
{% endhint %}
