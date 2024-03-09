---
description: 'Last revised: 16.01.2024'
---

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

### **Upsides**

1. **Broader Accessibility**🌐: Plasma allows assets to be sent to participants who were not originally part of the system, expanding its reach beyond initial users.
2. **Lower Capital Requirements** 💰: Unlike state channels, Plasma requires significantly less capital to be locked up, making it more accessible for smaller-scale operations.
3. **High Transaction Throughput** 🚀: Plasma excels in handling a large volume of transactions, making it ideal for applications with high transactional demands.
4. **Customizability for Specific Use Cases** 🔧: Plasma chains can be tailored to meet the needs of specific applications, offering flexibility in their deployment.

### Downsides

1. **Regular Onchain Data Publication 📊**: Advances in validity proofs like ZK-SNARKs may mitigate the frequency and volume of on-chain data publishing required by Plasma, compared to its earlier versions.
2. **Delayed Withdrawals ⏳**: The challenge period in Plasma is necessary to prevent fraud, but new designs incorporating validity proofs could streamline withdrawals, potentially speeding up the process.
3. **Dependence on Asset Ownership Logic 🔑**: Plasma's effectiveness is contingent upon assets having a clear owner. New Plasma proposals seek to address assets without distinct economic ownership, though full security assurances remain intricate.
4. **Application-Specific Complexity 🧩**: Modern Plasma iterations are attempting to reduce the high levels of application-specific reasoning by improving EVM compatibility, thereby easing the creation of Ethereum-like systems.
5. **Limited Scalability in Complex Applications 📈**: Previous Plasma models were less suitable for complex applications. Introducing EVM capabilities and ZK-EVM advancements may extend Plasma's scalability to more sophisticated applications.
6. **Operator Dependence for Data Management 👥**: While initial Plasma models relied on operators for data management, potentially causing centralization, new models with enhanced validity proofs aim for a more decentralized approach, though some operator involvement persists.
7. **Data Availability Issues 🔒**: Data availability has been a critical issue for Plasma, but emerging proposals utilizing ZK-SNARKs could improve data verification, making it easier to spot and dispute invalid transactions.
8. **User Vigilance Requirement 👀**: Users must monitor the network or delegate the monitoring to ensure fund safety, adding complexity. However, recent Plasma developments could lessen this burden through better exit mechanisms and fraud detection.

## Optimal for 🎯

<details>

<summary><strong>Asset Tracking and Management</strong></summary>

Applications that require tracking and managing assets can benefit from Plasma chains. Each asset can be assigned a unique ID and tracked efficiently, making Plasma suitable for digital marketplaces, supply chain management, and tokenized asset platforms.

</details>

<details>

<summary><strong>Microtransactions or Frequent Small Transactions (i.e. Payments focused)</strong></summary>

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
3. [**OmiseGO's research implementation of Minimal Viable Plasma - GitHub**](https://github.com/omgnetwork/plasma-mvp): This GitHub repository contains OmiseGO's research implementation of Minimal Viable Plasma, offering a practical look at how MVP is structured and implemented.

### History

1. [**Original Plasma Paper**](http://plasma.io/plasma-deprecated.pdf) **Aug 2017:** The pdf file of the original Plasma paper
2. [**Minimal Viable Plasma - Ethereum Research**](https://ethresear.ch/t/minimal-viable-plasma/426) **Jan 2018**: This resource provides a specification for a minimal viable plasma implementation, discussing its basic security properties and functionalities.
3. [**Plasma MVP - Learn Plasma**](https://www.learnplasma.org/en/learn/mvp.html)**:** This page offers an overview of More Viable Plasma (MoreVP), an extension to Minimal Viable Plasma, and explains how Plasma MVP operates.
4. [**Plasma Cash**](https://ethresear.ch/t/plasma-cash-plasma-with-much-less-per-user-data-checking/1298) **Mar 2018**: A specific variant of the Plasma framework, designed to enhance the scalability and security
5. [**Plasma Cashflow**](https://hackmd.io/DgzmJIRjSzCYvl4lUjZXNQ?view#%F0%9F%9A%AA-Exit) **Summer 2018**: Outlines Plasma Cashflow as an adaptation of Plasma Cash, involving depositing, transacting, and exiting a specific blockchain chain. Also Mentions ways to address the costs associated with validating tokens, such as using zkSNARKs or Plasma XT-style checkpointing.
6. [**Plasma Prime**](https://ethresear.ch/t/plasma-prime-design-proposal/4222) **Nov 2018:** This proposal delves into the utilization of the UTXO model for defining asset ownership, the mechanics of RSA proofs for transaction inclusion and exclusion within specified segments, the detailed structure of Plasma blocks
7. [**Exit games for EVM Validiums: The return of Plasma**](https://vitalik.eth.limo/general/2023/11/14/neoplasma.html) **Nov 2023:** The article revisits Plasma in light of advancements in validity proofs, such as ZK-SNARKs, which could address Plasma's main challenges, especially in managing client-side data storage. It explores potential extensions of Plasma to the EVM with parallel UTXO graphs and total state exiting
