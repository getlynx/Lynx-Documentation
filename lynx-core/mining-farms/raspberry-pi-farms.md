---
cover: >-
  https://get.clevver.org/1e7da431df7fb4193126fb9a61b6feec011c9edecc2f12211d34cfb26185aa53.png
coverY: 0
---

# Raspberry Pi Farms

If you plan to use Raspberry Pi, we strongly recommend the Raspberry Pi 4 with 2GB of RAM. You could get the 4GB or 8GB configuration, but it won’t bring you better results. Remember, Lynx is hungry for more CPU threads, not RAM. A Raspberry Pi 4 has four core threads, and each thread will mine Lynx with the capacity to spare.

_Why is it important to have spare capacity on a Lynx node?_

Remember, a node has four primary (and optional) tasks.

1. Verify and relay transactions to peers.
2. Maintain an intact and verified copy of the complete publicly accepted blockchain.
3. Run a wallet.
4. Mine blocks and publishes them to peers for verification.

You must have spare capacity on the node so it can accept and verify blocks from its peers. The work to confirm a block and relay it to peers isn’t terribly processor intensive, but you need RAM, CPU, and drive capacity on the node to handle spikes in activity and log files that can grow large.
