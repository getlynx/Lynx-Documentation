---
description: A bootstrap file is a backup of the blockchain in a simple database flat file
cover: >-
  https://get.clevver.org/814127f288e59e0148153a4c7b64be4d4d7164d321b7f0ec0b550546257bb4d1.png
coverY: 0
---

# Bootstraps

#### Lynx Bootstrap files are regularly created and posted on the [Official Lynx Bootstrap Repo at Github](https://github.com/getlynx/LynxBootstrap/releases). These are the trusted bootstraps created by the Lynx Core team.

### Create a Lynx Bootstrap Archive

The [following script will allow you to create your own backups](https://github.com/getlynx/LynxBootstrap/blob/master/archive.sh) of the Lynx Blockchain. When the script is completed, you will have a list of segments and a single manifest file. Save all of these together. The manifest file provides hashes of the segments for verification purposes for reassembly.

> wget -qO - https://raw.githubusercontent.com/getlynx/LynxBootstrap/master/archive.sh | bash

{% hint style="success" %}
The archive script is designed to scale well. As the Lynx Blockchain gets larger over time, a single bootstrap.dat file can become large and difficult to handle. The archive script creates segments of the larger file that are 125MB in size. They are labeled in order, and a manifest file of hashes is designed to ensure that the files are undamaged during the reassembly process.&#x20;
{% endhint %}

### Extract a Lynx Bootstrap Archive

The [following script will allow you to reassemble the segments](https://github.com/getlynx/LynxBootstrap/blob/master/extract.sh) created from the above script into a single, usable bootstrap.dat file. The script will place the newly created bootstrap.dat file in the \~/.lynx directory on your Lynx node. It would be best if you restarted the Lynx daemon manually after the bootstrap file had been created. The Lynx daemon will notice its presence on a restart and index it. This process can take a while but left alone, it will be completed without error.

> wget -qO - https://raw.githubusercontent.com/getlynx/LynxBootstrap/master/extract.sh | bash

For research purposes, the extract script above allows tag parameters if you prefer to restore a bootstrap tag that is not the latest version. The newest version is always the default if the tag parameter is not supplied.

> wget -qO - https://raw.githubusercontent.com/getlynx/LynxBootstrap/master/extract.sh | bash -s v10.0-mainnet

## LynxCI Installer

The LynxCI installer script handles the above restore processes for you. The script will automatically pull down the latest bootstrap files and reassemble them. If you are installing Lynx on Linux with the LynxCI installer script or ISO for Pi, you don't need to do any of these steps - they are automated.
