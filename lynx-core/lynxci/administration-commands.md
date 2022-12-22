---
cover: >-
  https://get.clevver.org/d75ac685012511a4cf1696ac6c5ed10ec1dd32cfa30c769aa35bc7563678f0b3.png
coverY: 0
---

# Administration Commands

LynxCI has some built-in commands that make Linux administration fast and easy. The following commands will make operating your cloud VPS or Raspberry Pi 4 simple. These special commands are not part of Lynx but modifications made to the Linux operating system used on your cloud VPS or Raspberry Pi. These commands only work if you use LynxCI or the ISO for Pi. When logged into the lynx user account, the following commands are available. _They do not work as the ‘root’ user._

## $ doc <a href="#ee84" id="ee84"></a>

Display a list of commands available and shortcuts that will make Linux Administration of the Lynx daemon easier.

## $ lyl <a href="#eeb3" id="eeb3"></a>

_Abbreviation for ‘lynx log.’_

It displays the filtered Lynx debug log quickly and only shows the information you are most interested in. Specifically, the command reveals the built-in miner statistics, status, and latest block tip detected by peers. This command will be the most common command you use to check the status of your Lynx node.

Also, you will see this command is executed automatically when you first log into a LynxCI node.

## $ tail -F -n 1000 \~/.lynx/debug.log <a href="#df90" id="df90"></a>

Displays the unfiltered live streaming debug log. It can be overwhelming at times but helpful when troubleshooting.

## $ lyc <a href="#a167" id="a167"></a>

_Abbreviation for ‘lynx configuration.’_

This command allows you to view and edit the lynx.conf file quickly. This command enables quick access to the Lynx configuration file. The lynx.conf file is preconfigured for you. It is well documented, and few changes will ever be needed. If you make any changes, you must restart Lynx.

The ‘cpulimitforbuiltinminer’ parameter is often modified to change the mining speed of the device. The default value is ideal for most users. If you change the ‘cpulimitforbuiltinminer’ parameter, keep the same decimal format and closely monitor your temperature and CPU thread usage. Rarely is a value over ‘0.90’ a good idea. If you are changing values in this file and using a Raspberry Pi, [be sure to understand why the values might change on their own](https://docs.getlynx.io/lynx-core/lynxci/thermal-controls). Be sure to save your changes. If you make any changes, you must restart Lynx.

## $ lyw <a href="#fc40" id="fc40"></a>

_Abbreviation for ‘lynx wifi.’_

When LynxCI is running on a Raspberry Pi via the ISO, this command helps configure the wireless features of the Raspberry Pi. Replace the wireless SSID username and password values with the default listed values. You may need to reboot your Raspberry Pi after making this change gracefully.

## $ lyt <a href="#14af" id="14af"></a>

_Abbreviation for ‘lynx temperature.’_

Displays the temperature of your Raspberry Pi. This command only works for Raspberry Pi. The objective is to keep the Pi temperature below the maximum operating temperature threshold of 85 C. _The value output is a five-digit value. ie. 45765 = 45.7 celsius_

## $ sudo systemctl restart lynxd <a href="#cc48" id="cc48"></a>

Restarts the Lynx daemon. You may be prompted for your lynx user account password. This is normal.

## $ lyf <a href="#d788" id="d788"></a>

_Abbreviation for ‘lynx firewall.’_

Display the current firewall settings. This command reveals what IPs will be allowed access and the respective ports.

## $ lyi <a href="#1635" id="1635"></a>

_Abbreviation for ‘lynx iptables’_

View and edit the firewall settings. This command allows you to edit the firewall configuration. The firewall is configured to be secure by default. Be sure to read the notes in the file for further customization.

## $ tipsy <a href="#1656" id="1656"></a>

If you are a member of the Lynx Discord, you can register with the Tipsy bot for free. You can register your LynxCI node or Raspberry Pi to double your mining rewards and automatically enter to win more Lynx. Display more instructions to get registered.

## $ htop -t <a href="#2ed6" id="2ed6"></a>

This Linux package will provide insight into the CPU load. It is recommended not to have a CPU load average higher than 90% capacity.
