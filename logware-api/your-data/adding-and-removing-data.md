---
cover: >-
  https://get.clevver.org/8f971ce11cc184a51c9a58582bb1b7860c4d37f31dd281cdc45f9604977bdbd1.png
coverY: -215.82733812949638
---

# Adding and Removing Data

A blockchain is, simply put, a particular type of database. While it might not offer a traditional relational database's native read and write speeds, it provides a few additional features not found before in the relational database. For example, unlike other data storage mechanisms, permanence is a feature delivered by blockchain technology. Once information is committed to the blockchain, it can't be changed, assuming the Proof of Work is adequately secure. This design is why blockchain technology is excellent for tracking value. "Store of value" blockchains like Bitcoin and Monero are examples of these. Lynx is a utility blockchain that primarily stores data, but it relies on the same technology. Once committed, this design enforces confidence it will remain unchanged as long as the blockchain is supported.

The design of blockchain defines data can only be added, never deleted. But the use of encryption can render information inaccessible. A good strategy is for the client to implement a standard encryption scheme on the stored data and create a 'denylist' of Transaction Ids locked from the decryption process. This 'denylist' should also get stored on the blockchain as an encrypted payload. The application is written to only honor the newest 'denylist' payload. This client still holds the keys to decrypt the data but not always. For example, some payload encryption schemes might only store Salt while the customer retains the decryption password.

One of our senior Logware engineers is happy to consult with your team to discuss how your application can best secure its data.
