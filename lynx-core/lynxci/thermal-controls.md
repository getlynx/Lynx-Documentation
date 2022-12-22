---
description: The LynxCI Mining Thermostat
cover: >-
  https://get.clevver.org/7af29bfe442ddd86cfecc72e83286b0dbb379adb6a680cd32ef417157838e7c0.png
coverY: 0
---

# Thermal Controls

Most Lynx mining enthusiasts know that Lynx comes with a built-in miner that works well for solo mining, even on the Raspberry Pi. The [Raspberry Pi 4](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/) (2GB) is recommended for the best results at the lowest price. With the [LynxCI ISO](https://github.com/getlynx/LynxCI/releases/tag/v27-ISO) image, enthusiasts can get the Pi mining in minutes! It’s enjoyable, works as a great training tool to understand solo mining, and supports the Lynx network.

A recurring discussion in the Lynx community about LynxCI revolves around the relationship between the temperature of the Raspberry Pi and mining speed. LynxCI, by default, does not overclock or max out the CPU capacity of the Raspberry Pi processor, but the device can still get pretty warm, depending on the type of fan used and the ambient temperature of the room. So some [unique](https://github.com/getlynx/LynxCI/blob/c4c47abe35578db6a72c5e8871312745e06dcd89/install.sh#L228) code was written to automate the temperature of the Raspberry Pi while still extracting maximum performance from the Raspberry Pi CPU.

The code is a thermostat, but we call it the _LynxCI Temperature Service_. It’s included in LynxCI and works only on the Raspberry Pi.

{% hint style="warning" %}
The temperature service is ignored on VPS installations of LynxCI as temperatures are regulated differently for those environments.
{% endhint %}

LynxCI starts to collect a 5-minute average of the current temperature every hour. The value is then compared to some built-in thresholds. The Lynx configuration script is automatically updated if the temperature is too high to lower the miner CPU consumption by 10%. If the temperature falls below the threshold, the Lynx configuration script is updated to allow the CPU to run faster (by 1%). In both cases, the Lynx daemon is restarted, and mining resumes. After a new install of LynxCI, the device might restart the Lynx daemon several times as it acclimates to the environment the Pi is located. If the room's temperature is stable, the Pi will eventually find itself mining most efficiently with an optimum CPU amount. To ensure the most extended life of your Pi, it is recommended not to override or change the default threshold amounts.

{% hint style="info" %}
If you are not interested in using the temperature service, you can always disable it by tuning the systemd service with the command “sudo systemctl stop lyt”. The command “sudo systemctl disable lyt” will permanently turn it off after a restart.
{% endhint %}

So you are interested in making sure your Pi is mining as fast as possible? All you need to do is cool it better! No need to adjust any settings on the Pi. Acquire a larger fan for your Raspberry Pi, or place it in a cooler room. The Pi will detect the lower temperatures and respond automatically by mining faster.

You can always review the temperature history and mining speed changes by typing the command “lyt” when logged in as the lynx user on your Raspberry Pi. The command will display the recent temperatures detected and how the LynxCI responded by increasing the speed, lowering the speed, or keeping the rate unchanged.

We love our Lynx community of Raspberry Pi solo miners. We hope you like this new feature.
