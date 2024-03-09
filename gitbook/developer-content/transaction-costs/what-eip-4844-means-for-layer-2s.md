# 🖼 What EIP 4844 means for Layer 2s

Just like discussed in the context of [onchain-data-availability](../../general-layer-2-knowledge/data-availability/onchain-data-availability/ "mention") options, EIP 4844 introduces a new Ethereum transaction format the 'BLOB\_TX\_TYPE', designed specifically for short-term data storage in a more affordable manner.

## **What are Blobs?**

1. **Definition**: BLOB (Binary Large OBject) is a large packet of data (4096 field-elements of 32 bytes each) that is separate from the traditional transaction data or calldata in Ethereum. They are specifically formatted and intended for on-chain data storage, but only short-term, as they are pruned after approximately 2 weeks.
2. **Purpose**: Blobs are used to store large amounts of data that don’t need to be executed by the Ethereum Virtual Machine (EVM) but are necessary for verification within the Ethereum Blockchain. This is particularly crucial for rollups, which process transactions offchain and require onchain data availability for the security and finality of the Layer 2 state.
3. **Home**: A blob is not housed on the execution layer but rather on the consensus layer of the beacon chain. This arrangement stems from the fact that blobs do not need to interact natively with transactions but simply require storage. Initially up to 16 blobs per Ethereum block will be permitted, which translates to a maximum storage increase of 2 MB per block (4096 \* 32 bytes \* 16 per block). Assuming a constant price auction, this would result in an approximate 0.75 MB increase of storage availability. This upgrade will therefore boost Ethereum’s storage capabilities by 40% over the theoretical maximum size of a block today (30M gas divided by 16 gas per byte = 1.875MB).

### **Where Do Blobs Come From?**

1. **Origin**: Blobs are not derived from the data of the current or previous blocks in the traditional sense. Instead, they are created as part of specific transactions, known as blob-carrying transactions ('BLOB\_TX\_TYPE'). These transactions are designed to include these large data packets and nothing more.
2. **Use Case**: A common use case for blob storage is to store transaction data and state roots from Layer 2 scaling solutions. Rollups process transactions off-chain to reduce the load on the main Ethereum chain. The resulting data receipts, which need to be available on-chain for security and validation purposes, are packaged into blobs.

### **How are Blobs Different from Regular Transaction Data?**

1. **Storage and Processing**: Unlike regular transaction data that is processed and stored by all nodes, blobs are meant to be stored temporarily (\~ 2 weeks) and are not processed by the EVM, adding no additional burden on the EVM execution layer.
2. **Accessibility**: The content of a blob is not directly accessible in the execution environment. Instead, the transaction carrying the blob includes commitments to the blobs. These commitments are accessible in the execution environment, while the actual data is shared and validated among the beacon chain nodes.
3. **Temporary Nature**: Blobs are stored on the Ethereum network only for a limited period (\~ 2 weeks). After this period, the data can be pruned to free up space, as its immediate availability is no longer critical.

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
   * This process ensures data availability without necessitating that the data be processed through calldata, which would permanently store the data on Layer 1.
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
