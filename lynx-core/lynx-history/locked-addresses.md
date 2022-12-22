---
description: Why were two suspicious addresses locked?
cover: >-
  https://get.clevver.org/98f348f9d7dac2cd580122445e8e28779771dc92dadb1f086df34d27c9a18c25.png
coverY: 0
---

# Locked Addresses

In short, because the addresses contain provably stolen coins.&#x20;

_A bit of history._ Long ago, regarding the block numbers listed below, someone attacked Kittehcoin (before the Lynx development team took over the project). The attack exploited a weakness that allowed the attacker _to define the amount of mining reward_. At that time, the default mining reward was only 2,000 MEOW per block. However, the blocks below show the reward was changed to the same 2 _billion_ each time the attack was executed. The pattern is easy to find. The Lynx team fixed the security hole when they ported the latest Litecoin code to the (previouslt named) Kittehcoin chain. While the attack vector was closed, the coins still remained in existence, pumping up the circulating supply by ±28 billion coins.

* Block: 1327713 — Coinbase Reward: 2,000,000,000 — Address: [K7Z3uThEHim6hvQBa1kqb6jwhp9QfynbyM](https://chainz.cryptoid.info/lynx/address.dws?K7Z3uThEHim6hvQBa1kqb6jwhp9QfynbyM.htm)
* Block: 1327710 — Coinbase Reward: 2,000,000,000 — Address: [KPwNzFNnEUcKfiuW4dyVwm9sKvY9rP24Cp](https://chainz.cryptoid.info/lynx/address.dws?KPwNzFNnEUcKfiuW4dyVwm9sKvY9rP24Cp.htm)
* Block: 1327704 — Coinbase Reward: 2,000,000,000 — Address: [KDbND8WQSXDhmEhEaV62TUH5GJaYxaVXVx](https://chainz.cryptoid.info/lynx/address.dws?KDbND8WQSXDhmEhEaV62TUH5GJaYxaVXVx.htm)
* Block: 1327689 — Coinbase Reward: 2,000,000,000 — Address: [KJqhouB6FX2xnZkGqFXCR5NMdrBgYzgcyd](https://chainz.cryptoid.info/lynx/address.dws?KJqhouB6FX2xnZkGqFXCR5NMdrBgYzgcyd.htm)
* Block: 1327646 — Coinbase Reward: 2,000,000,000 — Address: [KKquAGVnSt33WpvRbYPhCcBuaqMSskkjDB](https://chainz.cryptoid.info/lynx/address.dws?KKquAGVnSt33WpvRbYPhCcBuaqMSskkjDB.htm)
* Block: 1327595 — Coinbase Reward: 2,000,000,000 — Address: [KGaQrKE4jNzS44ZAukmLCpX1jGgsNcJNqE](https://chainz.cryptoid.info/lynx/address.dws?KGaQrKE4jNzS44ZAukmLCpX1jGgsNcJNqE.htm)
* Block: 1313353 — Coinbase Reward: 2,000,000,000 — Address: [KFu5EBViCUuUQPNufc3LEQAThVBhfP2LZz](https://chainz.cryptoid.info/lynx/address.dws?KFu5EBViCUuUQPNufc3LEQAThVBhfP2LZz.htm)
* Block: 1313352 — Coinbase Reward: 2,000,000,000 — Address: [KEgVoShXe1uManCMWB7mifFyzDB6EjGibi](https://chainz.cryptoid.info/lynx/address.dws?KEgVoShXe1uManCMWB7mifFyzDB6EjGibi.htm)
* Block: 1299977 — Coinbase Reward: 2,000,000,000 — Address: [KJ2eg8U4vqHjThLx7tpW1TovgWgURYo5Mx](https://chainz.cryptoid.info/lynx/address.dws?KJ2eg8U4vqHjThLx7tpW1TovgWgURYo5Mx.htm)
* Block: 1299963 — Coinbase Reward: 2,000,000,000 — Address: [KEcJNXRM2JZKskLy7Fw3KtQqPhcczmEV3o](https://chainz.cryptoid.info/lynx/address.dws?KEcJNXRM2JZKskLy7Fw3KtQqPhcczmEV3o.htm)
* Block: 1293504 — Coinbase Reward: 2,000,000,000 — Address: [KFFjYVKCbsQhWdEDFegCjNVugp4fE3Gmpu](https://chainz.cryptoid.info/lynx/address.dws?KFFjYVKCbsQhWdEDFegCjNVugp4fE3Gmpu.htm)
* Block: 1293496 — Coinbase Reward: 2,000,000,000 — Address: [KNJpmWvoBnQ8fLkqoi8SbRBE1xBTrybZz4](https://chainz.cryptoid.info/lynx/address.dws?KNJpmWvoBnQ8fLkqoi8SbRBE1xBTrybZz4.htm)
* Block: 1286358 — Coinbase Reward: 2,000,000,000 — Address: [KATtxFYoMwdcQJVsCJVDz2VD8K2KUpwqHt](https://chainz.cryptoid.info/lynx/address.dws?KATtxFYoMwdcQJVsCJVDz2VD8K2KUpwqHt.htm)
* Block: 1256813 — Coinbase Reward: 2,000,000,000 — Address: [KJxF5BY5zenfHtWrKGEEcPggRiJZFFrbJT](https://chainz.cryptoid.info/lynx/address.dws?KJxF5BY5zenfHtWrKGEEcPggRiJZFFrbJT.htm)

The code change implemented in v0.16.3.9 includes a restriction for the [2 largest known single addresses on the Lynx blockchain:](https://chainz.cryptoid.info/lynx/#!rich)

* KJ2MGS3jq4DPkVmE1ephMCbT7ojDcDSJRG
* KSho9zUYrFdTPPxfF6ye9sLurgKygeUEzL

The attacker(s) now has 2 options:

Option 1: Do nothing.

* The coins in those wallets will never be spendable. All future version of Lynx will include the lockdown code that will prevent the coins from being spent. Consensus of the network prevents the coins from being moved.

Option 2: Release the coins in exchange for a bounty.

* Each of the two blocked addresses may keep 100,000,000 Lynx in their original addresses _IF they send the rest of coins to this — and only this — address:_ [KQoKm4bzQvDAwiiFsPz3AE4UJHkHBvX6Bz](https://chainz.cryptoid.info/lynx/search.dws?q=KQoKm4bzQvDAwiiFsPz3AE4UJHkHBvX6Bz). Once the coins are received, the blocking code will be removed in future Lynx releases and the 100,000,000 coins will revert to the attackers’ control.
* If the coins are ever received at that address, a small portion of them will be used to reimburse the few Lynx holders that experienced theft (approximately Dec 5, 2019) from an R-value Attack. Then, the remainder of the coins will be verifiably burned. A schedule will be published and the remaining stolen coins will be burned.

Why are we burning the stolen coins?

We’re burning the stolen coins because it’s the right thing to do. We have no interest in keeping them because it will erode trust in the Lynx project, and that’s something we take very seriously. These coins were created outside of the normal business rules of Lynx. Therefore, all Lynx holders paid for them. Lynx never had a pre-mine or ICO. The existence of the stolen coins harms every Lynx holder by suppressing the total value of the network market cap and reducing the total scarcity of the circulating supply. If these coins are burned, the total circulation should be reduced by roughly \~20%. We expect this will have a positive impact on the entire Lynx network — _and the community of users that support it._

Note: our general policy is to not police the Lynx blockchain. However, we made an exception here because of the size of the theft, the number of users it impacts (everyone), and it’s easy to trace on the blockchain. It’s our hope that most of the Lynx community accepts and supports this difficult decision.
