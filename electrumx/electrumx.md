---
description: Lynx is fully supported for the Lightweight Electrum Server in Python
cover: >-
  https://get.clevver.org/8714ee8fa2372ef404ad8bb0ff09b949677aa39b4c649da9b932f42f69b1e386.png
coverY: 0
---

# Build Script Details

The Github Repository for the Lynx ElectrumX build script is located [here](https://github.com/getlynx/LynxElectrumBuilder). Suggestions are welcome at Github or on the [#electrum-team channel of the project Discord](https://discord.getlynx.io/).

The build script relies on a few dependencies and ties them together in a single script that completes the tedious task of building the Electrum. The scripts include;

* [LynxCI](https://github.com/getlynx/LynxCI) - the script to create a Lynx node.
* [Electrum Installer](https://github.com/MadCatMining/electrumx-installer) - from our friends at [Mad Cat Mining](https://mcmpool.eu/) - who generously upgraded the [upstream version](https://github.com/bauerj/electrumx-installer) to work with Debian 11 and the latest versions of Python for Debian 11.
* [Certbot](https://certbot.eff.org/) - to complete the task of ensuring that all connections to the Electrum remain encrypted.
* Shell scripting - the auto-configuration of Electrum configuration files, Lynx configurations files,  and local firewall settings on the node.

{% hint style="info" %}
The complete documentation for ElectrumX can be found [here](https://electrumx-spesmilo.readthedocs.io/en/latest/). All Lynx ElectrumX servers enforce secure traffic via ports 50002 and 50004. Non-secure Electrum ports are blocked.
{% endhint %}

## Reference Configuration Files

The following files are automatically configured in the [build script,](https://github.com/getlynx/LynxElectrumBuilder) but sometimes, a copy of a configuration file is helpful. Below is a template of your local /etc/electrumx.conf file.&#x20;

```bash
# This script is for electrum.getlynx.io. Be sure to update your domain below.
# File location: /etc/electrumx.conf

DB_DIRECTORY=/db
DAEMON_URL=http://{localLynxRPCUsername}:{localLynxRPCPassword}@127.0.0.1:9332/
COIN=Lynx
DB_ENGINE=rocksdb
COST_SOFT_LIMIT=0
COST_HARD_LIMIT=0
SSL_CERTFILE=/etc/letsencrypt/live/electrum5.getlynx.io/fullchain.pem
SSL_KEYFILE=/etc/letsencrypt/live/electrum5.getlynx.io/privkey.pem
SERVICES=ssl://:50002,wss://:50004,rpc://
REPORT_SERVICES=wss://electrum5.getlynx.io:50004,ssl://electrum5.getlynx.io:50002
```

The following Class should be used to correctly integrate your Electrum node with Lynx. The Lynx [Discord Community Volunteers](https://discord.getlynx.io/) manage the current list of peers in this list.&#x20;

```bash
# For Debian 11
# File location: /usr/local/lib/python3.9/dist-packages/electrumx/lib/coins.py

# https://docs.getlynx.io/electrumx/
class Lynx(Coin):
	NAME = "Lynx"
	SHORTNAME = "LYNX"
	NET = "mainnet"
	P2PKH_VERBYTE = bytes.fromhex("2d")
	P2SH_VERBYTES = (bytes.fromhex("16"),)
	WIF_BYTE = bytes.fromhex("ad")
	GENESIS_HASH = ('984b30fc9bb5e5ff424ad7f4ec193053'
			'8a7b14a2d93e58ad7976c23154ea4a76')
	DESERIALIZER = lib_tx.DeserializerSegWit
	TX_COUNT = 1
	TX_COUNT_HEIGHT = 1
	TX_PER_BLOCK = 1
	RPC_PORT = 9332
	PEER_DEFAULT_PORTS = {'t': '50004', 's': '50002'}
	PEERS = [
		'electrum5.getlynx.io s t',
		'electrum6.getlynx.io s t',
		'electrum7.getlynx.io s t',
		'electrum8.getlynx.io s t',
		'electrum9.getlynx.io s t',
	]
	REORG_LIMIT = 5000

```
