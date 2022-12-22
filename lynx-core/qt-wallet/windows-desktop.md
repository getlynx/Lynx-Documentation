---
cover: >-
  https://get.clevver.org/51daae86413a48d283ac46a50c380f454c343e13e13053d604766dea80c4bc8a.png
coverY: 0
---

# Windows Desktop

In December 2021, the latest version of the Lynx QT (GUI) wallet was released. This wallet includes the latest revisions and upgrades to the built-in miner. Once your version is running, you will find it leverages all available cores efficiently, and the number of blocks found will increase over the previous version release.

Some issues are reported with the latest version, 'v0.16.3.12'. These complications arise from the QT wallet UI and the built-in miner. Upon start, the wallet will appear frozen or stuck, but the client is running. Verify this by viewing the debug.log file and observing the latest records at the bottom of the file.

The QT wallet will not start mining until the wallet sync's with the network, so if your wallet appears frozen, quit the program and add the following lines to your lynx.conf file.

{% code title="lynx.conf" %}
```
disablebuiltinminer=1

addnode=node.getlynx.io
addnode=node.getlynx.art
addnode=node.getlynx.cat
addnode=node.getlynx.org
addnode=node.getlynx.xyz
```
{% endcode %}

Save your file change and start your Lynx client again. It should start up quickly and sync with the network after a short while. All wallet functions should operate properly, except the miner is disabled, of course.

To enable the built-in miner, be sure you have funded addresses in the wallet (at least 1000 Lynx per address) OR specify funded addresses for the built-in miner to use. These might be addresses in a cold wallet or another personal wallet you control elsewhere. Add the following lines to your lynx.conf file.

{% code title="lynx.conf" %}
```
mineraddress=myLynxAddress1 
mineraddress=myLynxAddress2
mineraddress=myLynxAddress3
mineraddress=myLynxAddress4

addnode=node.getlynx.io
addnode=node.getlynx.art
addnode=node.getlynx.cat
addnode=node.getlynx.org
addnode=node.getlynx.xyz
```
{% endcode %}

Use the built-in Typsy Miner functions for an even faster start by simply adding your TipsyId to the lynx.conf file. The row to add to your file will look like this. After you add it, restart Lynx.

{% code title="lynx.conf" %}
```
tipsyid=myTipsyId

addnode=node.getlynx.io
addnode=node.getlynx.art
addnode=node.getlynx.cat
addnode=node.getlynx.org
addnode=node.getlynx.xyz
```
{% endcode %}

If you don't have a TipsyId, you can learn more [about the process here](https://medium.com/lynx-blockchain/how-to-register-your-miner-with-tipsy-in-lynxci-493aa63cceb7).
