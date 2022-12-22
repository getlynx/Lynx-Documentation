---
description: >-
  In the Lynx Core Installer, the script creates a lynx.conf file and inserts
  default configuration settings tested and proven to work well for most
  installations.
cover: >-
  https://get.clevver.org/d75ac685012511a4cf1696ac6c5ed10ec1dd32cfa30c769aa35bc7563678f0b3.png
coverY: 0
---

# Wallet Functions

The configuration file contains a setting to enable or disable the built-in wallet functions. When the wallet is enabled, the Lynx node can generate addresses to receive Lynx coins and send them. When the wallet is disabled, these functions are not available.

By default, wallet functions in LynxCI are disabled. There are two security reasons.

1. [LynxCI](./) is used on Raspberry Pi computers, and small-sized cloud compute instances. Both of these types of computers are created and destroyed quickly. If an administrator fails to back up a wallet, the wallet and its respective coins are lost forever. By disabling the wallet functions by default, the user is protected from costly mistakes.
2. Risk of theft. We took every precaution to create a secure Lynx node with LynxCI, but someone might try to hack your computer and steal your Lynx coins if incentives exist. Again, keeping the wallet disabled by default is the safest state.

If you comprehend the risks and would like to enable your wallet functions, change the 'disablewallet' parameter from '1' to '0' in the lynx.conf file. Then restart Lynx to commit the change.

If you change this value to '0' and someone knows your RPC username and password, all your Lynx coins in the respective wallet will probably be stolen. The Lynx development team can not get your stolen coins back. You are responsible for your coins. If the wallet is empty, it's not a risk, but make sure you know what you are doing.

{% hint style="info" %}
In order for someone to connect to your node via RPC, you must enable access to the [Lynx RPC port](../lynx-ports.md). If you actively block the RPC port, you add an additional security layer against bad actors.
{% endhint %}
