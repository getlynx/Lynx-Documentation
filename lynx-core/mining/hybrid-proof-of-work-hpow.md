---
description: >-
  Lynx implements a series of business rules that must be met by the miner and
  verified by peers to get a candidate block accepted by the network
  successfully.
cover: >-
  https://get.clevver.org/814127f288e59e0148153a4c7b64be4d4d7164d321b7f0ec0b550546257bb4d1.png
coverY: 0
---

# Hybrid Proof of Work

### Summary

1. A single miner can’t win a block more than once every 60 blocks.
2. The miner’s reward address balance must be greater than or equal to a required fluctuating minimum amount of Lynx to win a block.
3. By using random selection, the fastest miners are not always guaranteed to win the block reward.

### Detail

1. The first rule requires that the miner’s address not have been the recipient of a mining reward in the previous 60 blocks. The address supplied within the candidate block coinbase header value is checked during verification by other nodes. If a match occurs during the last, rolling 60 blocks, the candidate block gets refused even if they have the fastest solve time for the hash. The verification fails, and the block candidate is considered invalid.
2. The second HPoW Rule requires the address supplied for the coinbase reward to have a minimum balance when the candidate block is submitted. The minimum amount is the difficulty value of the previous 10th block from the current block solved multiplied by the power of 4. Again, a minimum and a maximum balance of 1,000 and 100,000,000 Lynx, respectively, is required.
3. The third HPoW Rule concerns the reward address submitted in the candidate block. After executing a single SHA256 hash on the miner’s reward address, the last three characters found must match the last three characters of the block hash value submitted by the miner in the candidate block. Forcing a match randomizes who can win the block. Even the fastest miner can’t be guaranteed to win the block or a series of blocks in succession. The chances are 1 in 4,096 that a block candidate submitted will be able to win the block.

Additionally, Hybrid Proof of Work gets verified by peers on the network during the verification phase. Thus, it’s easy to see if a submitted block is valid. Due to the low miner reward, the intended network topology would ideally consist mainly of low-power mining computers. As a result of the HPoW rules, the likelihood is that every miner who complies could win a block, not just the most powerful miner. These business rules won’t work well for mining pools, so solo miners will become the primary method of mining Lynx.

