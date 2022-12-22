---
cover: >-
  https://get.clevver.org/d9a18131199dcfbe735751ad7386d573912e098bb73a84ef60bc84833b369cba.png
coverY: 0
---

# Local Mining

Local Mining means that your built-in miner is using addresses that are held in the locally enabled wallet on your Raspberry Pi, QT wallet, or VPS node.&#x20;

The wallet is usually enabled on a Lynx node, and this would mean Local Mining is the default mining method. You will need to have Lynx cryptocurrency in the local wallet for the built-in miner to start. (There are alternatives, that are discussed later.) This is also called a ‘hot wallet,’ which means the wallet is active and contains real Lynx cryptocurrency. If someone gained access to your computer, they could steal your coins by sending them somewhere else, so be careful you always lock your computer and enable your backups.

The wallet has a ‘Receive’ function that gives you an address to receive coins from a friend or exchange. Have a friend send 1001 Lynx to your new ‘Receive Address.’

{% hint style="info" %}
Why 1001? Because they might subtract the transaction fee from the amount sent, you would get less than 1000 Lynx! This would put your address balance under the 1000 Lynx requirement, and the miner would ignore that respective address.
{% endhint %}

Once the coins are received by your wallet and a few block confirmations have passed, Lynx will notice the new balance and start mining. Lynx will check the balance of each of your addresses in your wallet and randomly select an address to mine that has a balance equal to or greater than 1000 Lynx. Having more Lynx in an address does not help you win a block faster, and having more addresses with Lynx will not help either. The miner randomly selects a funded address - how many coins are in the address does not impact the random selection.

Another fundamental factor when mining Lynx is that an address, once it’s won a block, can’t win another block until 60 blocks have passed. So if you are mining with only one address, you can only win a block once every 60 blocks. That is not great, so the way around this is to have many addresses in your Local Wallet that have a balance of 1000 Lynx. We recommend at least 50 addresses. Once you win a block, your Lynx built-in miner will automatically rotate to a different address and resume mining. It all happens automatically; all you have to do is fund your addresses with Lynx. This design is similar to Proof of Stake mining, with the difference being that you don’t get more significant results if you are richer. Lynx treats everyone the same, rich or poor. Each address has a chance, as long as it has a balance of 1000, respectively.

If you are considering Local Mining for your Raspberry Pi or VPS, you should have a good wallet backup strategy in place. If the node goes down and you lose the wallet you will be glad you backed it up. If you are running many Pi's in a Farm, this can be tedious to set up and manage. We recommend Remote Mining for individuals that wish to build a mining farm. The security of the nodes is much easier, consumes less time and you will earn more Lynx over time too.
