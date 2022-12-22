---
description: >-
  In the Lynx Core Installer (LynxCI), the installer creates a lynx.conf file
  and inserts default configuration settings that are tested and proven to work
  well for most installations.
cover: >-
  https://get.clevver.org/59dfd8bfcbe3708216e58eed79c4a5d976093abf8be54c8be13800b1603ccf40.png
coverY: 0
---

# Default Addresses

During the Lynx Core Installer (LynxCI) installation process, default Lynx addresses are inserted into the Lynx configuration file.

{% hint style="info" %}
After logging in as the ‘lynx’ user, you can easily view this file by typing ‘lyc’ (short for ‘Lynx configuration’).
{% endhint %}

Because Lynx has a slightly modified Proof of Work algorithm (Hybrid Proof of Work), Lynx uses a built-in miner enabling users to solo mine Lynx coins without using mining pools, expensive hardware, or third-party mining software. All mining functions are bundled into Lynx, and LynxCI configures it for you upon installation.

Lynx requires at least one reward address to start mining — this is the address where mining rewards + fees are sent if your Lynx miner wins a block. The default configuration contains five addresses, and they are unique. The default five addresses are controlled and owned by the Lynx Core development team, so any mining rewards + fees earned will go to them. This is the most secure and quickest way to get your miner running. The wallet is not enabled, and no coins are stored on the disabled wallet. Nothing can be stolen or lost, yet the miner can still run.

Eventually, you will want to change the five default mining addresses in the Lynx configuration file to yours. **You should get the coins you mine!** Copy/paste Lynx addresses from another wallet to the Lynx configuration file, replacing the existing values. Be sure to keep the same format. Also, you MUST have a balance of at least 1,000 Lynx in each address you place in the configuration file. This requirement results from the slightly modified Proof of Work algorithm used by Lynx.

{% hint style="info" %}
The Lynx Code development team recommends installing the Desktop QT wallet on your macOS or Windows computer. Either buy or borrow enough Lynx, so your QT wallet addresses have at least 1,000 Lynx. Sometimes 1,005 is best to cover transaction fees. Use these addresses in your LynxCI node. Creating 10 or 20 addresses is a great idea, and the same address list CAN be used on all your LynxCI nodes (Raspberry Pi or Cloud computers).
{% endhint %}

When your LynxCI computer wins a block, the mining reward will be sent to your Desktop QT computer. Be sure to keep your wallet encrypted and backup often. If something terrible happens to your LynxCI node, you won’t lose your coins — they are safe on your Desktop!

{% hint style="warning" %}
Power Tip: You don’t have to keep your Lynx Desktop QT wallet running to receive your mining rewards, they will show up automatically, and you will see them the next time you start your wallet. If you decide to keep your Lynx Desktop wallet running, the built-in miner will run there, so you will have two computers mining Lynx! Great job!
{% endhint %}

{% hint style="success" %}
For an even easier mining configuration using your LynxCI, please review the Tipsy Miner article and learn how to double your mining rewards & automatically enter to win a lottery with each won block for a chance to win over 1 million Lynx.
{% endhint %}
