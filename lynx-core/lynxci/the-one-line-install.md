---
cover: >-
  https://get.clevver.org/c8398789c2c5d097944250dd8d53f168c4bddf46c2c95e4d70bcb77dec53647f.png
coverY: 0
---

# The One Line Install

The one-line installer is excellent for root access on the target computer or VPS. This installer is not designed for Windows or Mac computers.

{% hint style="danger" %}
_**Do not use this installer on Windows or Mac operating systems; only execute this script as root on a freshly installed Linux operating system.**_
{% endhint %}

You can execute the one-line command once you are logged into an Ubuntu 20.10, Ubuntu 20.04 LTS, Raspberry Pi OS, Debian 11, or Debian 10 root account. We don’t recommend you use ‘sudo’ from a non-root account.

{% hint style="info" %}
Debian 11 is the recommended Linux flavor for LynxCI.
{% endhint %}

[You can watch LynxCI install](./); it only takes about 5 minutes on most computers. It will reboot the computer or VPS and begin the blockchain sync process when it's done. After a 20-minute wait, the Lynx node will finish syncing with the global network and then start mining with the default addresses. To speed up the process, LynxCI uses the latest bootstrap file. It is downloaded automatically and indexed as part of the LynxCI installation.

There are two ways to use LynxCI. You can use the one-line install script command or use the ISO image to flash an SD card for your Raspberry Pi.
