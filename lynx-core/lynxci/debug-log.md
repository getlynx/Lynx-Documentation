---
cover: >-
  https://get.clevver.org/1c501e05d2a252a28b46fa7971e0b5b4782e16f1ebcceb20dd28701f74cce197.png
coverY: 0
---

# Debug Log

In the [Lynx Core Installer (LynxCI)](https://github.com/getlynx/LynxCI), the installer creates a lynx.conf file and inserts default configuration settings tested and proven to work well for most installations.

The path to the default debug log of your LynxCI Mainnet node is

> /home/lynx/.lynx/debug.log

The path to the default debug log of your LynxCI Testnet node is

> /home/lynx/.lynx/testnet4/debug.log

The debug log is capable of outputting a massive amount of data. Since LynxCI is pretty well tested, most debug information collected is about the miner. This is the default setting. For a complete list of debug options, browser the list below. Restart Lynx to commit the change and see the new debug output in the respective file path.

\- net\
\- tor\
\- mempool\
\- http\
\- bench\
\- zmq\
\- db\
\- rpc\
\- estimatefee\
\- addrman\
\- selectcoins\
\- reindex\
\- cmpctblock\
\- rand\
\- prune\
\- proxym\
\- empoolrej\
\- libevent\
\- coindb\
\- qt\
\- leveldb\
\- miner (default for LynxCI)\
\- 0 (all off)\
\- 1 (all on)

> If you are chasing a bug, set the argument to ‘debug=1’. It isn’t recommended to leave that log level intact, though. It will generate a great deal of data and could shorten the life of an SD card on a Raspberry Pi. If you have limited drive space, you might run out. So be aware of your drive space consumption.

{% hint style="success" %}
LynxCI includes a log rotation service that will first compress and eventually delete the Lynx debug.log file. This prevents the hard drive from filling up over time. No configuration is needed. All archived logs are kept in the same directory as the current debug.log.
{% endhint %}
