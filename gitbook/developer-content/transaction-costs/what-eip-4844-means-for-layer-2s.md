# 🖼 What EIP 4844 means for Layer 2s

Just like discussed in [onchain-data-availablity](../../general-layer-2-knowledge/data-availability/onchain-data-availablity/ "mention") in the context of Data Availability options EIP 4844 introduces a new transaction format, the "blob-carrying transactions", designed to slash gas fees :fuelpump: and supercharge scalability.

## **What are Blobs?**

1. **Definition**: BLOBs (Binary Large OBjects) are large packets of data that are separate from the traditional transaction data in Ethereum. They are specifically formatted and intended for use in scaling solutions, particularly Layer 2 solutions like rollups.
2. **Purpose**: Blobs are used to store large amounts of data that don't need to be processed by the Ethereum Virtual Machine (EVM) but need to be available for verification or future use. This is especially important for rollups, which process transactions off-chain but require data availability on-chain for security and finality.
3. **Content and Format**: A blob is a package of data, often formatted in a specific way to align with Ethereum's data structures. For example, in EIP4844, a blob is defined as a collection of elements from a specific scalar field, suitable for cryptographic processes.

### **Where Do Blobs Come From?**

1. **Origin**: Blobs are not derived from the data of the current or previous blocks in the traditional sense. Instead, they are created as part of specific transactions, known as blob-carrying transactions. These transactions are designed to include these large data packets.
2. **Use Case**: A common source of blobs is from Layer 2 networks or rollups. These networks process transactions off-chain to reduce load on the main Ethereum chain. The resulting data, which needs to be available on-chain for security and validation purposes, is packaged into blobs.

### **How are Blobs Different from Regular Transaction Data?**

1. **Storage and Processing**: Unlike regular transaction data that is processed and stored by all nodes, blobs are meant to be stored temporarily and are not processed by the EVM. This reduces the computational burden on the network.
2. **Accessibility**: The content of the blob is not directly accessible in the execution environment. Instead, the blob-carrying transaction includes commitments to the blobs. These commitments are available in the execution environment, while the actual data is shared and validated differently.
3. **Temporary Nature**: In some proposals, blobs are stored on the Ethereum network only for a limited period (e.g., a few days or weeks). After this period, the data can be pruned to free up space, as its immediate availability is no longer critical.

## **EIP 1559 Explained**

EIP 1559, introduced to Ethereum in 2021, overhauled the network's transaction fee mechanism. Here's a breakdown of its key features:

1. **Base Fee and Tip**: Each transaction now includes a base fee, which is burned (removed from circulation), and a tip, or priority fee, paid to miners for faster processing.
2. **Dynamic Base Fee**: The base fee adjusts dynamically per block, increasing when the network is congested (more than 50% full) and decreasing when it's less used.
3. **User Experience**: Users can better estimate fees since the base fee is algorithmically determined based on the previous block's demand, improving predictability.

### **Blobs Fee Market**

Now, integrating this understanding with the Blobs Fee Market:

1. **Separate Fee Market for Blobs**: Just like EIP 1559 sets a dynamic base fee for regular transactions, the Blobs Fee Market establishes a separate pricing mechanism for blob-carrying transactions. This ensures that the large data packet transactions do not affect or get affected by regular transaction fees.
2. **Dynamic Blob Fee**: Similar to EIP 1559's base fee, the blob fee adjusts based on network demand, but independently of the regular transaction fees.
3. **Max Fee Per Blob Gas**: Users specify the maximum fee they are willing to pay per unit of blob gas, akin to the tip in EIP 1559. This ensures that their transaction will be processed if the set fee is above the current blob fee.

## **Scenario**

Let's consider a real-world analogy to simplify this:

* **EIP 1559 (Regular Transactions)**: Imagine a highway with a dynamic toll system. When the highway is busy, the toll increases to reduce traffic and vice versa. Each car (transaction) pays a base toll (base fee) that is used for highway maintenance (burned) and can pay extra (tip) for priority lanes.
* **Blobs Fee Market (Large Data Packets)**: Now, consider a separate set of lanes on this highway specifically for trucks carrying heavy loads (blob-carrying transactions). These lanes have their own toll system, independent of the car lanes. The toll for trucks adjusts based on how busy these lanes are, ensuring that truck traffic does not interfere with car traffic and vice versa.
* **Application in Ethereum**: In Ethereum, regular transactions (cars) and large data packet transactions (trucks) coexist. By having separate fee mechanisms, both can operate efficiently without overwhelming the network, ensuring a smoother flow of both regular transactions and large-scale data operations.

## **Layer 2 Rollups post-EIP4844**

1. **Blob-Carrying Transactions**:
   * Layer 2 rollups will package their data into blobs.
   * These blobs are then included in blob-carrying transactions on the Ethereum mainnet.
   * This process ensures data availability without requiring the data to be processed or permanently stored on Layer 1.
2. **Data Availability without Burden**:
   * The blobs ensure that the necessary data for rollup transactions is available on the Ethereum mainnet for a certain period.
   * However, since these blobs are not processed by the Ethereum Virtual Machine (EVM), they don't add computational load to the mainnet.
3. **Temporary Storage**:
   * The blobs are stored on the Ethereum network for a limited time (e.g., several days or weeks).
   * After this period, the data can be pruned as its immediate availability is no longer critical for the security and operation of the rollups.
4. **Security and Verification**:
   * Even though the blobs' data isn't processed by the EVM, it's still essential for verifying the correctness of the rollups' transactions.
   * The availability of this data on the mainnet means that any user or smart contract can potentially verify rollup transactions if needed.
5. **Cost Efficiency**:
   * EIP4844 aims to make the cost of data storage more predictable and efficient for Layer 2 solutions.
   * By separating the fee market for blob data from regular transaction fees, Layer 2 rollups can operate with better cost certainty.
