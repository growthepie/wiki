# ⚡ Plasma

## Scenario 🌟

**Imagine a digital art marketplace, where artists and collectors buy, sell, and trade unique digital artworks. In this marketplace, Plasma technology is used to manage transactions efficiently and securely.**

**Depositing Artwork:**

1. **Artist Submission** 🎨: An artist, let's call her Ava, creates a digital artwork and decides to sell it on the marketplace. She deposits her artwork into the marketplace's smart contract, which is managing the Plasma chain.
2. **Unique Identification** 🔢: The smart contract assigns Ava's artwork a unique ID, say 537, ensuring it's distinct and traceable within the Plasma chain.

**Plasma Chain Operation:**

1. **Chain Operator** 🔗: The marketplace has a designated operator for the Plasma chain. This could be a centralized entity, a group operating under multisig, or a decentralized system like Proof of Stake (PoS).
2. **Batch Creation** ⏲️: Every 15 minutes, the operator gathers all transactions made off-chain on the Plasma chain. These transactions include sales, purchases, and trades of digital artworks.
3. **Merkle Tree Generation** 🌳: The operator generates a Merkle tree from these transactions. In this tree, each index corresponds to a transaction involving a specific artwork ID. If no transaction exists for an artwork, that part of the tree remains empty.
4. **Publishing and Notification** 📢: The operator publishes the Merkle root of this tree to the Ethereum main chain. They also send the Merkle branch corresponding to each artwork to the current owner, ensuring they have the proof of ownership.

**Withdrawing Artwork:**

1. **Collector's Withdrawal** 💼: A collector, let's call him Ben, who recently purchased Ava's artwork (ID 537), decides to withdraw it from the Plasma chain to his private wallet.
2. **Initiating Withdrawal** 🚀: Ben publishes the Merkle branch showing the most recent transaction where he received the artwork from Ava.
3. **Challenge Period** ⏳: The smart contract initiates a 7-day challenge period. During this time, others can present evidence using other Merkle branches to prove that either Ava didn't own the artwork when she sold it or that she sold it to someone else after Ben.
4. **Successful Withdrawal** 🏆: If no one successfully challenges Ben's claim within 7 days, he is allowed to withdraw the artwork, transferring it securely to his private wallet.

## Ups and Downs :arrow\_up::arrow\_down:

**Upsides:**

1. **Broader Accessibility**🌐: Plasma allows assets to be sent to participants who were not originally part of the system, expanding its reach beyond initial users.
2. **Lower Capital Requirements** 💰: Unlike state channels, Plasma requires significantly less capital to be locked up, making it more accessible for smaller-scale operations.
3. **High Transaction Throughput** 🚀: Plasma excels in handling a large volume of transactions, making it ideal for applications with high transactional demands.
4. **Customizability for Specific Use Cases** 🔧: Plasma chains can be tailored to meet the needs of specific applications, offering flexibility in their deployment.

**Downsides:**

1. **Regular Onchain Data Publication** 📊: Plasma necessitates the publication of a hash on the blockchain at regular intervals, unlike state channels which require no onchain data during normal operations.
2. **Delayed Withdrawals** ⏳ : The challenge period required to prevent fraudulent activity can lead to delays in withdrawing assets from the Plasma chain.
3. **Dependence on Asset Ownership Logic** 🔑: Plasma's security relies on the premise that each asset has a logical owner. If the owner is indifferent or the asset lacks clear ownership (like in Uniswap), Plasma may not function effectively.
4. **Application-Specific Complexity** 🧩: Implementing Plasma requires a significant amount of application-specific reasoning, making it challenging to create a system that fully simulates the Ethereum environment or the EVM.
5. **Limited Scalability in Complex Applications** 📈: Due to its inability to support general computation, Plasma is less suitable for applications requiring complex interactions or state changes.
6. **Operator Dependence for Data Management** 👥: It relies on one or more operators for data storage and management, which can create centralization issues.
7. **Data Availability Issues** 🔒 : Compared to ZK-rollups and optimistic rollups, Plasma faces challenges in data availability. If the operator withholds data, it becomes difficult for users to challenge invalid transactions.
8. **User Vigilance Requirement** 👀: Users must regularly monitor the network or delegate this responsibility to ensure the safety of their funds, adding an extra layer of complexity.



## Optimal for 🎯

<details>

<summary><strong>Asset Tracking and Management</strong></summary>

Applications that require tracking and managing assets can benefit from Plasma chains. Each asset can be assigned a unique ID and tracked efficiently, making Plasma suitable for digital marketplaces, supply chain management, and tokenized asset platforms.

</details>

<details>

<summary><strong>Microtransactions or Frequent Small Transactions</strong></summary>

Plasma is ideal for applications involving frequent, small-value transactions. This could include gaming platforms, micropayment systems, or any application where users frequently exchange small amounts of value.

</details>

<details>

<summary><strong>Non-Financial Applications</strong></summary>

Due to its lower capital requirements and ability to handle a diverse range of transactions, Plasma is also suitable for non-financial blockchain applications that still require the benefits of decentralization and security.

</details>

### Not suitable for

<details>

<summary>Applications requiring instant transaction finality or those that involve complex state transitions</summary>



</details>

## Examples and resources 📚

1. [**The Development and Prospect of Plasma - Medium**](https://medium.com/@Web3comVC/the-development-and-prospect-of-plasma-42eed0838a3f): This article discusses the current state and future potential of Plasma, highlighting its design space and scalability solutions.
2. [**Ethereum Plasma: Everything You Need to Know - OKX**](https://www.okx.com/learn/ethereum-plasma-guide): A guide that explores Ethereum Plasma, detailing how it creates smaller chains on top of an existing child chain and its implications for the blockchain ecosystem.
3. [**Original Plasma Paper**](http://plasma.io/plasma-deprecated.pdf)**:** The pdf file of the original Plasma paper
4. [**Plasma Cash**](https://ethresear.ch/t/plasma-cash-plasma-with-much-less-per-user-data-checking/1298): A specific variant of the Plasma framework, designed to enhance the scalability and security
5. [**Minimal Viable Plasma - Ethereum Research**](https://ethresear.ch/t/minimal-viable-plasma/426): This resource provides a specification for a minimal viable plasma implementation, discussing its basic security properties and functionalities.
6. [**Plasma MVP - Learn Plasma**](https://www.learnplasma.org/en/learn/mvp.html)**:** This page offers an overview of More Viable Plasma (MoreVP), an extension to Minimal Viable Plasma, and explains how Plasma MVP operates.
7. [**OmiseGO's research implementation of Minimal Viable Plasma - GitHub**](https://github.com/omgnetwork/plasma-mvp): This GitHub repository contains OmiseGO's research implementation of Minimal Viable Plasma, offering a practical look at how MVP is structured and implemented.



