---
cover: >-
  https://get.clevver.org/d75ac685012511a4cf1696ac6c5ed10ec1dd32cfa30c769aa35bc7563678f0b3.png
coverY: 0
---

# Firewall Security

LynxCI comes with a built-in firewall management service. For the first seven days after the installation of LynxCI, direct SSH access via port 22 is unrestricted. After seven days of uptime, the firewall service resets itself and restricts SSH access to a shortlist of IP addresses.

The built-in firewall service will keep away port scanners, bad actors, and bots that might be probing your network. Within the first seven days, you are recommended to change the default list to IP addresses that you wish to allow. A Virtual Private Network (VPN) IP access point is recommended for stable access from home and office for VPS nodes. Consult the Administration Commands for more information on updating the firewall service.
