---
cover: >-
  https://get.clevver.org/d75ac685012511a4cf1696ac6c5ed10ec1dd32cfa30c769aa35bc7563678f0b3.png
coverY: 0
---

# Mining Lynx is different

The Lynx cryptocurrency has several built-in features that discourage mining for profit. Lynx lacks incentives to mine compared to other projects. There are several economic, financial, regulatory, philosophical, and technical reasons. Below are some of the barriers and explanations.

#### If you are mining and you win a block, the block reward of 1 lynx sent to your mining address must wait for 20,000 Lynx blocks to pass before spending.

This means you can’t send that 1 Lynx you just mined to another address or exchange until the Lynx has aged 20,000 blocks. That is a long time and a good reason to keep a detailed account of your mining addresses and wallets. Once the coins have become ‘mature,’ they can be spent. This impacts the [velocity of money](https://www.investopedia.com/terms/v/velocity.asp) aspect of the Lynx Cryptocurrency.

#### The mining reward for Lynx is one coin.

This is a meager reward amount due to the value of a single Lynx coin being so low. Sure, a single Bitcoin is worth a significant amount of money, but a single Lynx is practically worthless. This removes the incentive to attract for-profit miners from entering the Lynx mining space. Additionally, miners with expensive equipment need to support the hardware and electricity costs. Mining Lynx isn’t attractive to them because the numbers don’t work. This is why mining with a Raspberry Pi 4 appeals to participants. The cost of entry is low, and the risk of getting bumped by more prominent players with fancy equipment is also common.

This isn’t to say that fancy ASICs don’t occasionally show up on the Lynx network. They do, but they don’t stick around long.

#### The address that received the block reward is then restricted from winning another block in the next 60 block window.

When a miner wins a block, 1 Lynx is sent to the respective miner's address. If you are mining with only one address, instead of having a chance of winning each block, you have a chance of winning a block only every 60 blocks — regardless of the hashing power of your CPU, GPU or ASIC. This creates a severe throttle for mining pools and powerful mining hardware, requiring them to rotate addresses. It poses an interesting challenge as the previously won addresses need to be tracked, and new fresh addresses that haven’t won need to be available. This is a result of Hybrid Proof of Work Rule 1. You can read more about HPoW in the Lynx Whitepaper available on the Lynx website. Inspiration for this feature was a [Tesla Valve](https://en.wikipedia.org/wiki/Tesla\_valve).

#### For a miner to use an address to mine, the address must have a minimum balance of at least 1000 Lynx in it at the time of its usage.

This concept is borrowed from the idea of Proof of Stake. Unlike PoS, having more than 1000 Lynx in the address does not increase the likelihood of winning the block. It’s simply a minimum requirement to win a block. Over time, the 1000 Lynx minimum fluctuates and correlates to the ‘network difficulty rate’ of Lynx. As Lynx grows in popularity and the number of mining nodes increases globally, a built-in secondary algorithm throttles the growing number of miners. The cost of funding a lynx address for mining increases over time. This is the result of Hybrid Proof of Work Rule 2.

#### There is a 1 in 256 chance that when a miner assembles a block and submits it to peers, the network will accept it.

This throttle restricts the likelihood of a candidate block created by a miner from being accepted by peers. This has a considerable impact on block time and network hash requirements. No longer are miners that possess the fastest hardware and fastest network connection guaranteed to win the most block rewards. With the business rule described, miners now enjoy an almost random distribution of block rewards. Even a low-powered device like a Raspberry Pi can win a block before a well-funded competitive miner. Hybrid Proof of Work Rule 3 governs this built-in throttle's proper functioning.
