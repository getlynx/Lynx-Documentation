---
description: Flash your Raspberry Pi for quick setup.
cover: >-
  https://get.clevver.org/e1558faf4dbc30d5867df194fa35a1899b00409f43a76836fb63233ffdd1bca1.png
coverY: 0
---

# ISO for Raspberry Pi

Support for the Raspberry Pi is available in an ISO image that is flashed onto an SD card, then inserted onto the Pi device. The ISO image is only for the Raspberry Pi. While the ISO will work on Pi's with 1GB of RAM, it will be sluggish, and mining should be disabled. Raspberry Pi devices with 2GB of RAM or more will work well. The built-in miner can be enabled for those devices with successful outcomes of around one block per day and up. A fan is recommended for your Pi, as the CPU can get quite warm. To keep CPU temperatures within tolerance, built-in thermal controls will regulate the speed of the built-in miner.

For the latest version of the Raspberry Pi ISO, please visit the LynxCI Releases website and look for the latest ISO release. The file will be compressed with a file format similar to '[2021-01-11-LynxCI.tar.gz](https://github.com/getlynx/LynxCI/releases/download/v27-ISO/2021-01-11-LynxCI.tar.gz)'.

We have found [Raspberry Pi Imager](https://www.raspberrypi.com/software/) to be very easy to use. On another computer, start the Imager program. Use the option "Use Custom", then select this uncompressed file that you downloaded from the LynxCI Github Releases website. Flash the SD card with the ISO. This process takes about 1 minute on a sufficiently speedy SD card. Then insert the card into the SD card slot on the bottom of the Raspberry Pi and power it on. No keyboard, mouse or monitor is required. You must plug in an ethernet cable connection to the device. A Pi 4 will be fully functional in about 20 minutes (it will take about 4x longer on a Pi 3). Here is an article that explains in more detail the [whole process](https://medium.com/lynx-blockchain/intermediate-using-the-lynx-cryptocurrency-installer-lynxci-363b00784a34).

{% embed url="https://youtu.be/ntaXWS8Lk34" %}
For the LynxCI ISO, be sure to select "Use Custom" when picking an image to flash.
{% endembed %}
