---
description: No ASICS found here. The built-in miner is all you need.
cover: >-
  https://get.clevver.org/d9a18131199dcfbe735751ad7386d573912e098bb73a84ef60bc84833b369cba.png
coverY: 0
---

# Built-in Miner

The [LynxCI](../lynx-core/lynxci/) and [QT wallet](../lynx-core/qt-wallet/) versions released from the Lynx Core Project team include a modified built-in miner that conforms to the Hybrid Proof of Work Rules defined in the [Lynx Whitepaper](https://getlynx.io/whitepaper).

No additional mining hardware is needed to mine Lynx. No ASICs or graphics card hardware setup is required. Lynx is only interested in the number of cores your CPU has. It will allocate a mining thread per CPU core, so the more cores available - the more mining it can do.

The miner is enabled in the Lynx.conf file with the parameter "disablebuiltinminer." (The default state of the miner is enabled.) If the value of this parameter is "1", the miner will not start. If the value is "0", the miner will begin when Lynx starts. If you change this parameter value, you must restart Lynx to commit the change.

If you have enabled the built-in miner with the parameter setting "disablebuiltinminer=0", you can tune the miner's speed. The speed is adjusted with the parameter "cpulimitforbuiltinminer." The expected range of values is within "0.01" to "0.99". The higher the number, the more CPU power the miner will consume.

{% hint style="info" %}
Mining Lynx is not a profitable endeavor, so it's unlikely you want 99% of the CPU dedicated to the built-in miner. Your VPS or computer might become unresponsive, or worse; you might damage the device due to the heat emitted from the processor. Even if you have special fans, setting the value too high can damage your computer. If you use a VPS vendor and your CPU consumption level is too high, your VPS vendor might restrict or ban your account. The Lynx community mines Lynx to support the network and project. Also, self-interested parties that wish to ensure the stability of their data stored will mine Lynx. Alternatively, they don't do it for profit but to ensure the security and access of their data stored for the future.

**For a dedicated physical device, values higher than 90% are discouraged.**

**For a VPS vendor, values higher than 60% are discouraged.**

_A particular note about AWS:_ some instance types will allow you to consume an extraordinary amount of CPU, but this was designed for spike traffic, not consistent usage. If you use AWS and set your miner beyond 20%, you will incur costly overage fees. Please do your testing and ensure you have an instance that restricts overage fees for CPU consumption.
{% endhint %}

If the built-in miner is disabled, the "cpulimitforbuiltinminer" parameter is ignored.
