---
description: The following guide will help you build your own ElectrumX Lynx node quickly
cover: >-
  https://get.clevver.org/779c8077fa0c85606f82d48eae0c1f865d73af0f12f31ee14fd6010b18e9b343.png
coverY: 0
---

# Build Instructions

{% hint style="danger" %}
Building an ElectrumX on a Raspberry Pi is not recommended unless you ensure the Pi has a public IP address and permanent direct access to the web. It should have +4GB of RAM.
{% endhint %}

* Debian 11 is required. The build script is explicitly designed for Debian 11.
* This is for a CLI-only version of Debian. A desktop version of Debian is not recommended.
* Create a VPS instance with at least 2GB of RAM.
* The VPS should have no other services installed. This VPS instance will be a dedicated public Lynx node, Electrum server, and if you enable it, Lynx miner.

{% hint style="info" %}
The following steps should be completed in the exact order.
{% endhint %}

1. Create your 2GB Debian 11 VPS instance with your vendor. We recommend [Linode](https://www.linode.com/), [Digital Ocean](https://www.digitalocean.com/), [Scaleway](https://www.scaleway.com/), etc.
2. Get the public IP4 address for the VPS and notify the [#Electrum-Team channel on the Lynx Discord](https://discord.getlynx.io/). The Administrator will configure a DNS record and name for your IP4 address.
3. As the root user on your VPS, execute the following command - be sure to replace the domain name in the last part of the command with the one provided from [Discord](https://discord.getlynx.io/).

```
wget -O - https://electrumx.getlynx.io/ | bash -s electrum.domain.com
```

1. The process will run for a few minutes and eventually reboot the VPS instance when complete. You don't have to continue to the next step right away; we recommend waiting 15 minutes before the next step.
2. Log back into the VPS with the lynx account (the root account has been locked for security). The default username and password are lynx for both.
3. You will be prompted to change the lynx password. This is normal. Set your lynx account password. If you are logged out, log back into the lynx account. Again, this is normal.
4. As the lynx user, type 'sudo su' to access the root account.
5. As the root user, copy/paste the command you used above again (don't forget the domain name you assigned at the end). Run that command again.
6. This will configure Electrum for you, set up SSL, and adjust the firewall.
7. It will display the Electrum log and show its sync progress when it is complete. You can watch it or type 'control+C' to exit. You are now done. Once Electrum completes the sync process, the Electrum services will be public.
8. Don't lose your lynx account password. We do NOT recommend enabling the wallet functions in Lynx. This is for your security.

{% hint style="success" %}
Power User: You can do this if you want to enable the built-in miner. As the lynx user, type 'lyc' and change the parameter 'disablebuiltinminer' to '0'. We recommend leaving the 'cpulimitforbuiltinminer' parameter with a value of '0.50'. For best results, use your Tipsy Miner Id in the lynx.conf file. This will get you the best results and is more efficient for the built-in miner. When done, restart lynx with the command 'sudo systemctl restart lynxd'.
{% endhint %}

{% hint style="danger" %}
If you enable the built-in miner and use too much CPU, the Electrum will run slow and the VPS vendor might ban your instance. We don't recommend running the built-in miner more than 50%.
{% endhint %}
