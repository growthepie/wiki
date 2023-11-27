# 🌀 Rollups



### **Understanding the Layer 2 Landscape:**

1. **Plasma and State Channels - Full Layer 2 Schemes**: Plasma and state channels attempt to move both data and computation offchain. However, they face fundamental game theory challenges related to data availability, making it difficult to safely support all applications. They rely on an explicit notion of asset ownership, which limits their generality.
2. **Rollups - A Hybrid Approach**: Rollups represent a hybrid Layer 2 scheme. They move computation and state storage offchain but retain some data for each transaction on Layer 1 (Ethereum). This approach balances offchain efficiency with onchain data integrity.



## Scenario 🌟

**Let's consider a crowdfunding platform that leverages Rollups to efficiently manage and secure its transactions. This platform allows entrepreneurs to pitch their projects and receive funding from backers. Here's how Rollups are utilized in this scenario:**

### **Setting Up the Rollup:**

1. **Smart Contract with State Root**📜🌳: The platform operates on a smart contract on the Ethereum blockchain. This contract maintains a state root, which is the Merkle root of the state of the rollup, encompassing account balances, project details, funding amounts, and other relevant data within the rollup.
2. **Publishing Batches**🗜️: Entrepreneurs post their projects, and backers fund them. These activities generate numerous transactions. Periodically, a batch of these transactions is compiled in a highly compressed form. Each batch includes the previous state root and a new state root, which reflects the state after processing these transactions.
3. **Contract Verification**✅: When a batch is submitted to the blockchain, the smart contract verifies that the previous state root in the batch matches its current state root. If the match is confirmed, the contract updates the state root to the new state root.

### **Deposits and Withdrawals:**

1. **Depositing Funds**: When backers want to fund a project, they can deposit their funds into the rollup. These transactions have inputs from outside the rollup state. The transaction submitting the batch must transfer these assets to the rollup contract.
2. **Withdrawing Funds**: If a project reaches its funding goal and the entrepreneur withdraws the funds, or if a backer withdraws their pledge, these transactions have outputs to the outside. Upon processing the batch, the smart contract initiates these withdrawals.

### **Ensuring Integrity of State Updates:**

The key challenge is ensuring that the post-state roots in the batches are correct. If someone could submit a batch with any post-state root without consequences, they could, for instance, illegitimately redirect funds. To prevent this, the rollup uses one of two main solutions: Optimistic Rollups and Zero-Knowledge Rollups.



## Ups and Downs :arrow\_up::arrow\_down:

### Upsides

1. **Improved Scalability and Efficiency** 🗜️: Rollups employ advanced compression methods to minimize the onchain data footprint. By replacing data with computation wherever possible, they significantly improve efficiency.
2. **Cost-Effective Transactions** 📈: By using advanced compression techniques, Rollups reduce the on-chain data footprint, leading to lower gas costs. For instance, an ERC20 token transfer in a rollup can cost under 300 gas, compared to about 45,000 gas on the Ethereum base layer.
3. **Enhanced Security** :closed\_lock\_with\_key:: Rollups maintain a portion of data onchain, ensuring the integrity and security of transactions. This is crucial for applications where trust and transparency are paramount.

### Downsides

1. **Hardware and Cost Requirements for ZK-Rollups**:&#x20;
   * 💻 **Hardware Intensity**: Generating zero-knowledge proofs, a key component of ZK-Rollups, requires significant computational power, which can be hardware-intensive.
   * 💸 **Cost Implications**: This hardware requirement can translate into higher costs, potentially making ZK-Rollups a less accessible option for some users or developers, especially those with limited resources.
2. **Withdrawal Delays in Optimistic Rollups**:&#x20;
   * ⏳ **Challenge Period Delays**: Optimistic Rollups include a challenge period to ensure transaction integrity. This period can lead to delays in withdrawing funds.
   * 🕒 **Not Ideal for Time-Sensitive Transactions**: Such delays might be a drawback for transactions where time is of the essence, as immediate access to funds is not guaranteed.
3. **Data Bandwidth Limitations**:&#x20;
   * 🌐 **Underlying Blockchain Constraints**: While Rollups significantly improve scalability, they are still bound by the data bandwidth limitations of the underlying blockchain (e.g., Ethereum).
   * 🚧 **Scalability Ceiling**: This means that despite their efficiency, Rollups cannot achieve infinite scalability and are subject to the performance constraints of the base layer.
4. **Complexity in Implementation**:&#x20;
   * 🧠 **Technical Complexity**: Implementing Rollups, particularly ZK-Rollups, involves advanced cryptographic techniques, which adds a layer of complexity.
   * 🛠️ **Development Challenges**: This complexity can pose challenges for developers, requiring specialized knowledge and skills in cryptography and blockchain technology.

## Optimal For 🎯

{% hint style="info" %}
Toggle to see what these applications could be
{% endhint %}

<details>

<summary>General Purpose and Complex Applications</summary>



1. **DeFi Applications**: In the decentralized finance (DeFi) space, Rollups can be particularly useful. They provide the necessary scalability to handle complex financial transactions and interactions, such as trading, lending, and borrowing, while ensuring security and data integrity.
2. **NFT Marketplaces**: For Non-Fungible Token (NFT) platforms, Rollups offer an efficient way to manage a high volume of minting, buying, and selling activities. They reduce the gas costs associated with these transactions, making NFT trading more accessible.
3. **Smart Contract Execution**: Rollups are well-suited for applications that require complex smart contract interactions. By offloading computation offchain, they allow for more complex and computationally intensive contracts to be executed more efficiently than on the main chain.
4. **Cross-Chain Interactions**: For applications that require interactions across different blockchain networks, Rollups can facilitate more efficient cross-chain transactions and communication.
5. **Privacy-Focused Applications**: Especially with ZK-Rollups, there is an added layer of privacy since transaction data is compressed and validated through zero-knowledge proofs, making them suitable for applications that prioritize user privacy.
6. **Scalable DApps (Decentralized Applications)**: DApps that aim to scale without compromising on security and decentralization benefit from Rollups. They can handle more users and transactions without the typical bottlenecks of the main blockchain.
7. **Enterprise Blockchain Solutions**: For businesses and enterprises looking to leverage blockchain technology for supply chain management, identity verification, and other applications, Rollups provide a scalable and efficient solution.

</details>



{% hint style="warning" %}
If you are just interested in knowing which one would be your problem-solution fit for your project go straight to [transaction-costs](../../transaction-costs/ "mention") page to see their comparison and outlook.
{% endhint %}
