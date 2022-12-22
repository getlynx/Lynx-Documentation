---
cover: >-
  https://get.clevver.org/1a72956a0521f388e29c9a5c83d70e8a684079b371df56622033dca6cbc5c300.png
coverY: 0
---

# Cooling your Pi

{% hint style="info" %}
This article only applies if you disable the built-in [Thermal Controls of LynxCI.](../lynxci/thermal-controls.md)
{% endhint %}

If you decide to edit the default mining CPU amount of your Pi, you’ll need a fan to extend the life of the Pi. The ambient temperature of the room your Pi stack enclosure occupies is essential. How do you determine if Pi needs a fan or not? LynxCI has a built-in command that will display the temperature of the Pi in Celsius. The objective is to keep the Pi temperature below the maximum operating temperature threshold of 85 C.

You are strongly recommended not to overclock your Raspberry Pi — the benefits by far don’t outweigh the cost.

When connecting a fan to the GPIO pins on the board, you have two voltage options depending on your temperature readings. Option one is 3.3v, and option two is 5v. Many fans are designed for a 5v connection, but the fans can be noisy and sometimes too strong. We recommend trying the 3.3v GPIO pins because the fans will be quieter and slower. That brings down the noise and power draw, and the Pi’s will remain within a reasonable temperature range. Be sure to check the temperature, though. The Raspberry Pi 4 will slow down on its own if it isn’t cooled correctly, so getting this right is essential. If you don’t want to worry about getting it wrong, use the 5v connection.

The following GPIO map displays the pins you will use for your fan. The red fan cable plugins into the 3.3v or 5v pin, and the black fan cable plugs into one of the ground pins.

[https://www.raspberrypi.org/documentation/usage/gpio/](https://www.raspberrypi.org/documentation/usage/gpio/).
