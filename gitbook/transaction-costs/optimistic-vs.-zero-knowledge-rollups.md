# ⚔ Optimistic vs. Zero Knowledge Rollups

## A Quick Overview

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>Transaction Costs as of 26th November 2023</p></figcaption></figure>

### **Optimistic Rollups (e.g. Arbitrum, Optimism)**:

* **Mechanism**: These rely on a system of fraud proofs. The rollup contract maintains a comprehensive history of state roots and the hash of each transaction batch.
* **Fraud Proofs**: If someone detects an incorrect post-state root in a batch, they can submit a fraud-proof to the blockchain. This proof demonstrates that the batch was computed incorrectly.
* **Verification and Reversion**: The contract verifies the fraud proof. If it finds the batch to be indeed incorrect, it reverts that batch and all subsequent batches, maintaining the integrity of the system.
* **Assumption of Honesty**: Optimistic Rollups operate under the assumption that all transactions are valid by default, and only in cases of fraud are proofs required and checked.

#### Transaction Fees Calculation

* Optimistic = (L1 data publishing gas \* L1 gas price) + (gas usage on L2 \* l2 gas price)



### **ZK-Rollups (e.g. zkSync Era, Ploygon zkEVM)**:

* **Mechanism**: These use validity proofs, specifically ZK-SNARKs (Zero-Knowledge Succinct Non-Interactive Argument of Knowledge), to ensure the correctness of transactions.
* **Cryptographic Proofs**: Each batch includes a ZK-SNARK, which cryptographically proves that the post-state root is the correct outcome of executing the batch.
* **Efficient Verification**: Regardless of the size of the computation, the ZK-SNARK can be verified quickly on-chain, ensuring that only valid state changes are accepted.
* **Immediate Finality**: Unlike Optimistic Rollups, ZK Rollups provide immediate finality, as the validity of each batch is proven and verified before being accepted on the blockchain.

#### Transaction Fees Calculation

* Zero\_knowledge = ((L1 data publishing + L1 proof costs) \* L1 gas price) + (gas usage on L2 \* l2 gas price)

## Comparison and Outlook

<figure><img src="../.gitbook/assets/Screenshot 2023-11-26 165100.png" alt=""><figcaption><p>Rollups Comparison, <a href="https://vitalik.ca/general/2021/01/05/rollup.html">source</a>: Vitalik Buterin</p></figcaption></figure>

> "In general, my own view is that in the short term, optimistic rollups are likely to win out for general-purpose EVM computation and ZK rollups are likely to win out for simple payments, exchange and other application-specific use cases, but in the medium to long term ZK rollups will win out in all use cases as ZK-SNARK technology improves."
>
> Vitalik Buterin

## Scenario 🌟

Imagine you're a developer working on two different blockchain projects: a decentralized marketplace (Project A) and a high-frequency trading platform (Project B). You're considering using Layer 2 solutions to optimize transaction efficiency and cost, and you're torn between Optimistic Rollups and ZK Rollups. Understanding the differences in their costs and functionalities is crucial for your decision.

### **Project A: Decentralized Marketplace - Optimistic Rollups**

* **Nature of Project**: This marketplace involves various transactions like listing items, bidding, and final sales. Immediate finality of transactions is not critical, as there's usually a waiting period for bids and sales to conclude.
* **Why Optimistic Rollups?**:
  * **Simplicity**: Optimistic Rollups are straightforward and align with the marketplace's less complex transaction structure.
  * **Adoption Readiness**: They are closer to widespread adoption, offering a more stable and tested environment.
  * **Cost Consideration**: While they entail higher on-chain gas costs, the frequency of transactions in a marketplace (not too high) makes this a manageable expense.
  * **Withdrawal Period**: The longer withdrawal period is not a significant concern, as marketplace transactions don't demand immediate finality.

### **Project B: High-Frequency Trading Platform - ZK Rollups**

* **Nature of Project**: This platform requires rapid transaction processing due to the high volume and fast pace of trades.
* **Why ZK Rollups?**:
  * **Immediate Finality**: ZK Rollups offer instant transaction finality, crucial for the dynamic nature of trading.
  * **Lower Gas Costs**: They provide lower per-transaction gas costs, a significant advantage given the high volume of trades.
  * **Complexity Trade-off**: The complexity and higher off-chain computation costs are acceptable trade-offs for the efficiency gains in a trading environment.
  * **Generalization Challenge**: While more challenging to generalize, the specific nature of high-frequency trading fits well with the capabilities of ZK Rollups.

## **Key Differences**

* **Cost Efficiency**: For Project A (marketplace), the higher on-chain gas costs of Optimistic Rollups are offset by the lower frequency of transactions. In contrast, Project B (trading platform) benefits from the lower per-transaction costs of ZK Rollups due to its high transaction volume.
* **Transaction Finality**: The marketplace can afford the longer finality period of Optimistic Rollups, whereas the trading platform benefits from the immediate finality provided by ZK Rollups.
* **Technical Complexity**: Optimistic Rollups' simpler technology aligns with the marketplace's needs, while the trading platform can leverage the advanced technology of ZK Rollups despite its complexity.

## Summary

### Optimistic Rollups

* More straightforward and closer to widespread adoption.&#x20;
* Suitable for applications where immediate finality is less critical.
* Preferable for scenarios that require a simpler technological approach.
* Entail higher onchain gas costs. Feature a longer withdrawal period.

### ZK Rollups&#x20;

* Offer immediate transaction finality.
* Provide lower per-transaction gas costs, ideal for high-volume, fast-paced environments.&#x20;
* Complexity and higher off-chain computation costs are notable trade-offs.&#x20;
* More challenging to generalize for broad applications.&#x20;
* Rapidly evolving technology.

## Sources and Extra Material

1. [**An Incomplete Guide to Rollups - Vitalik Buterin's Blog**](https://vitalik.ca/general/2021/01/05/rollup.html): This comprehensive guide by Vitalik Buterin delves into the concept of rollups as a key scalability solution for Ethereum. It covers the background of layer-1 and layer-2 scaling, the mechanics of state channels, plasma, and rollups, and the distinctions between optimistic and ZK rollups. The article also addresses the challenges and potential of rollups in enhancing blockchain scalability.
2. [**The L2 Paradox**](https://twitter.com/joel\_john95/status/1727628204964225027)**:** A very interesting must-read thread that discusses the current stage of the rollups and asks important questions
3. [**ZK-Rollups vs. Optimistic Rollups: Understanding the Differences - Nervos Network**](https://www.nervos.org/knowledge-base/zk\_rollup\_vs\_optimistic\_rollup)**:** It contrasts their operational mechanisms, particularly focusing on their approaches to transaction validation and data handling.

{% embed url="https://twitter.com/joel_john95/status/1727628204964225027" %}

