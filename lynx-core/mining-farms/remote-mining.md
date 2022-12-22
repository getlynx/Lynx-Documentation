# Remote Mining

_LynxCI is configured to use Remote Mining by default. It’s the recommended mining method for Lynx farms and it’s the most secure method of mining Lynx._

Remote Mining is very similar to Local Mining with the fundamental difference being that it’s more secure because no local hot wallet is involved. Remote Mining uses addresses that are not located in a local, enabled hot wallet. Instead, like the name suggests, the addresses used are held elsewhere, maybe on another Lynx node or a paper wallet.

With Remote Mining, the built-in miner is using addresses that are explicitly listed in the lynx.conf file and the local wallet function has been disabled. To learn how to disable your wallet function in Lynx, refer to the ‘disablewallet’ parameter. The format for declaring your addresses is handled by the ‘mineraddress’ parameter in the lynx.conf file. You can list as many ‘mineraddress’ parameter values as you like in the lynx.conf file, but you are recommended to not exceed 200.

_Tip: If you enable the wallet, and fund the local addresses AND also list ‘mineraddress’ parameters in your lynx.conf file, Lynx will ignore the addresses in the enabled local wallet and use the ‘mineraddress’ params in the lynx.conf file._

The same requirements exist for Remote Mining addresses as Local Mining addresses. Use as many as you like, but no more than 200 and be sure that each has a balance of 1000 Lynx or more. Remote Mining is nice for the Raspberry Pi and cloud mining farms because the risk of losing coins is zero if an SD card fails in a Pi or a VPS is destroyed, lost or shut down. Any Lynx earned from mining are deposited to the Remote address that is managed on a different computer or paper wallet.
