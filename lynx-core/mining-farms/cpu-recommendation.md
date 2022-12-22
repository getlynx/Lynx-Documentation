---
cover: >-
  https://get.clevver.org/0d8ea054d7f86d9bc0267425676b2f84685194216731088da641179349852050.png
coverY: 0
---

# CPU Recommendation

{% hint style="info" %}
This article only applies if you disable the built-in [Thermal Controls of LynxCI](../lynxci/thermal-controls.md) on your Pi. Thermal controls do not operate on VPS nodes.
{% endhint %}

For the Raspberry Pi 4, we recommend a CPU max of 75%. This leaves the operating system capacity to handle spikes and other tasks needed to keep up to speed. If the device has a CPU max set too high, the Lynx node won’t talk to its peers fast enough and might not begin mining the latest block when it should. This will result in the node falling behind and never having enough time to mine a current block.

For cloud VPS nodes, we recommend 75% also, but you must check with your vendor. Some cloud vendor nodes will tell you two conflicting values. The Linux package ‘HTOP’ is beneficial in determining how much load a VPS (or Pi) is handling, but a VPS vendor doesn’t use that number to determine a VPS’s max CPU capacity. The vendor [Linode](https://www.linode.com/) tells you the CPU value on its website Dashboard, and it’s this value that you can tune your mining settings. You can set your Linode to run at 90% in some cases. But keep in mind that a 1GB [Linode](https://www.linode.com/) has only one thread, so it is only doing 25% of the work of a Raspberry Pi 4.
