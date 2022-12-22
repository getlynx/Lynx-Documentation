---
description: We recommend you familiarize yourself with the following original parameters.
cover: >-
  https://get.clevver.org/7af29bfe442ddd86cfecc72e83286b0dbb379adb6a680cd32ef417157838e7c0.png
coverY: 0
---

# Basic Paramters

### **disablewallet**

This legacy param has been part of Lynx for a long time, but it’s rarely used as often as it should be.

`disablewallet=1`

You are turning off the built-in wallet functions of the node. Recall that this is one of the four primary functions of the Lynx node. By disabling the wallet, you reduce the amount of work Lynx needs to do (granted, it’s not a lot). More importantly, you are removing an attack vector. You aren’t storing any cryptocurrency on the node by turning off the wallet. The target for bad actors is removed. (Some might think that having Lynx coins in a wallet with the wallet disabled might be a good security design. It is not; we strongly recommend against this. Unless you encrypt your wallet.dat file, your coins could still get lost, or worse; you will forget they are there and lose them by erasure.) If you are using a VPS or Pi and an attacker steals or takes over your VPS, you have no risk of losing coins if you don’t have a wallet enabled. Keeping Lynx running with the wallet disabled with the [mineraddress param](advanced-configuration.md) is the most secure implementation of Lynx. It will support the network and pose no risk of losing coins for the miner.

{% hint style="danger" %}
_It’s also nice to know you won’t lose any coins if you accidentally reformat a Raspberry Pi SD card, as this has happened to the Lynx Developers more than once._
{% endhint %}

### **debug**

There are several types of debug output. If you turn on the debug output fully, your drive fills up very quickly. Lynx does not have built-in Log Rotate functions, so you must manually purge your old log files. For most users, the setting debug=miner is ideal.

{% hint style="success" %}
LynxCI does implement a Log Rotate service, so overflowing debug files is never an issue.
{% endhint %}

### **txindex**

While not always needed, we recommend it be disabled by default. The format is;

`txindex=0`

### **testnet**

Lynx has an active testnet. For testing purposes, it runs faster than the mainnet. It is important to remember that the testnet can be purged and rebuilt without notice. Testnet coins have no value and are not actively traded. If you hold testnet coins, they could be rendered valueless at any time, so only use them for testing, not owning. If you are running a node on testnet, the param value looks like this;

`testnet=1`

Otherwise, for a node running mainnet, your lynx.conf file should have

`testnet=0`

If you are using [Lynx Cryptocurrency Installer (LynxCI)](lynxci/), all these parameters are preconfigured. We strongly recommend farms, and even solo miners use LynxCI.

\
