---
cover: >-
  https://get.clevver.org/4e4c669f2986adc25766967d2bb70a8d737face1616a94b7f93154025fe7d113.png
coverY: 0
---

# Advanced Configuration

Miner configuration is pretty much like the configuration you might be using with other mining projects, including a few goodies.

_You will want to keep your RPC credentials secret. If your wallet is enabled and someone gains access to your RPC credentials, they can steal your Lynx coins, and you can’t get them back._

Lynx provides a few extra params for your \~/.lynx/lynx.conf file. These include;

### **mineraddress**

If the local wallet is disabled, the miner won’t know where to send its mining rewards. That was why this param was created. The miner address format should look like this when used correctly;

`mineraddress=K8roku8PDsnX9a56DVZzEyJLbuBvF31Bb6`

It would help if you never had any value other than a legit Lynx address used with this param. Even a blank entry won’t work. You can duplicate as many of these lines as you like with other addresses. We recommend having a range of 25 to 200 addresses on your list.

### **disablebuiltinminer**

This param controls the on/off state of the built-in miner. IT professionals that run cryptocurrency exchanges and Electrum servers for SPV wallets are recommended to keep the built-in miner disabled. The format of the param should look like this;

`disablebuiltinminer=1`

To leave the miner running, the format is;

`disablebuiltinminer=0`

Be sure to restart Lynx to commit the change.

### **cpulimitforbuiltinminer**

If the built-in miner is enabled, the cpulimitforbuiltinminer parameter becomes active. Suppose this value is not found in the lynx.conf file, then the default value of 1% will be used. The default value of 1% is set low not to disrupt normal operations of the target operating system. This parameter is used to override the default. If you are using a Raspberry Pi 4, a value of 75% is the highest we recommend. For a cloud VPS, you can go higher with a higher value (with AWS, be very careful). Rarely is a setting over 70% on a laptop a good idea for a sustained period. The format for this param value is a decimal. A 75% CPU setting would look like this;

`cpulimitforbuiltinminer=0.75`

### **host**

For reporting purposes, this value is used to label your node remotely. It’s not a required param and has a reserved status for future use. When creating a Lynx Farm, we recommend setting this value equal to the computer's hostname. LynxCI does this for you automatically. This value has no impact on the normal functions of Lynx. When using LynxCI, this value is automatically set for you and mirrors the computer's hostname. It’s a great help when trying to find an errant Raspberry Pi on your home network. The format looks like this;

`host=lynxpi205887062`

