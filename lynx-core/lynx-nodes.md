---
description: A globally distributed list of public nodes
cover: >-
  https://get.clevver.org/122d01bc1abc3b974c771b4eef13ae2cc7aeb1bd4b3441c02b64ea14765ae5c8.png
coverY: 0
---

# Lynx Peer List

{% hint style="info" %}
In the [Lynx Core Installer (LynxCI)](https://github.com/getlynx/LynxCI), the installer automatically creates a lynx.conf file and inserts default configuration settings that are tested and proven to work well for most installations.
{% endhint %}

There is a section in the lynx.conf file for a listing of default nodes that are public and ‘well known’ to other global peers. These default nodes are listed with the parameter ‘addnode’. By default, LynxCI creates 5 nodes. These nodes are managed by the the Lynx Core development team and they are known to be stable and always up to date. The default list of mainnet nodes you will see in your lynx.conf file will look like this. The following list can be inserted into your Linux, Mac & Windows Lynx desktop client configuration file.

{% code title="lynx.conf" %}
```
addnode=node1.getlynx.io
addnode=node2.getlynx.io
addnode=node3.getlynx.io
addnode=node4.getlynx.io
addnode=node5.getlynx.io
```
{% endcode %}

The Lynx Code project maintains these five mainnet peer nodes. You don't need to use all five in your file. At least three are adequate.

{% hint style="info" %}
The Lynx testnet is temporarily disabled.
{% endhint %}
