# 📨 Messaging Latency and Cost

### **Messaging**

* The Rollup allows for seamless communication with Layer 1, enabling the transmission of arbitrary messages.
* Each protocol ensures the verifiable transfer of data to the intended chain.

**Latency from L1 to L2**:

* This refers to the duration required for a message to become accessible on the Rollup once it's included in an Ethereum block.

**Cost from L1 to L2**:

* The expense involved in sending a message from Ethereum to the Layer 2 Rollup.
* The Rollup processes the message using a system address, acting on behalf of the original sender from Layer 1.
* The sender on Layer 1 bears the cost of Layer 2 gas for message execution.

**Latency from L2 to L1**:

* This is the time taken for a message to be available on Ethereum after it’s recorded in a Rollup block and sequenced to Layer 1.

**Cost from L2 to L1**:

* The gas expense incurred for the verification and initiation of message execution on Ethereum, following its dispatch from the Rollup.
* This cost is covered by the Externally Owned Account (EOA) that triggers the claim transaction on Layer 1.
* It's important to note that this cost does not include the expenses arising from the operations performed as a result of the message.



<table data-full-width="true"><thead><tr><th>Messaging</th><th>OP Mainnet (Optimistic, EVM)</th><th>Base (optimistic, EVM)</th><th>Linea (zk, EVM)</th><th>Arbitrum One (Optimistic, EVM)</th><th>Polygon zkEVM</th><th>zkSync Era (ZK, EVM)</th></tr></thead><tbody><tr><td>L1 → L2 Latency</td><td>~1 minute</td><td>~1 minute</td><td>~17min</td><td>~6-9 minutes</td><td>~6-8 minutes</td><td>~2 minutes</td></tr><tr><td>L1 → L2 Cost</td><td>~38 000 L1 gas</td><td>~43 000 L1 gas</td><td>~66 000 L1 gas + ~71 000 L2 gas (in case of manual delivery)</td><td>No added cost</td><td>95000 L2 gas</td><td>No added cost</td></tr><tr><td>L2 → L1 Latency</td><td>7 days</td><td>7 days</td><td>8 to 32 hours</td><td>7 days</td><td>~1 hour</td><td>-</td></tr><tr><td>L2 → L1 Cost</td><td>600 000 L1 gas</td><td>600 000 L1 gas</td><td>~73 000 L2 gas*</td><td>60 000 L1 gas</td><td>95000 L1 gas</td><td>-</td></tr></tbody></table>

\*On Linea
