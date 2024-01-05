# ⌛ General  Stats

Below we have gathered information from [rollup.codes](https://www.rollup.codes/) about some general information about different rollups together to provide a comprehensive overview and comparison between these approaches.

1. **Block Time**:
   * The time interval between the creation of consecutive blocks in a blockchain. In Layer 2s, block time can be significantly shorter than on Ethereum's Layer 1, allowing for faster transaction processing.
2. **Gas Limit / Block**:
   * The maximum amount of computational effort (gas) that can be expended in a single block on Layer 2. This limit helps manage the block's size and the speed of block processing.
3.  **\*Gas Target / Block**:

    * Similar to the gas limit, this is a softer cap or target for the amount of gas usage per block. Layer 2s might use this to guide block producers towards an ideal block size based on EIP-1559.&#x20;

    Read more here: [what-eip-4844-means-for-layer-2s.md](../transaction-costs/what-eip-4844-means-for-layer-2s.md "mention")
4. **Sequencing Frequency**:
   * The frequency at which the rollup posts L2 transactions on Ethereum L1. The time varies based on the amount of calldata that must be posted on L1
5. **Finality**:
   * The time it takes for transactions to be considered irreversible. In Layer 2s, finality often depends on the underlying Layer 1 blockchain (Ethereum), as Layer 2s periodically commits state updates to Layer 1.



<table data-full-width="true"><thead><tr><th width="139">Metrics</th><th>Ethereum</th><th width="120">OP Mainnet (Optimistic, EVM)</th><th>Base (optimistic, EVM)</th><th width="226">Linea (zk, EVM)</th><th width="114">Arbitrum One (Optimistic, EVM)</th><th>Polygon zkEVM</th><th>zkSync Era (ZK, EVM)</th></tr></thead><tbody><tr><td>Block Time</td><td>12 seconds</td><td>2 seconds</td><td>2 seconds</td><td>12 seconds</td><td>250ms</td><td>Irregular*</td><td>5 seconds</td></tr><tr><td>Gas Limit / Block</td><td>30 million</td><td>30 million</td><td>30 million</td><td>61 million</td><td>32 million</td><td>30 million</td><td>80 million</td></tr><tr><td>Gas Target/ Block*</td><td>15 million</td><td>5 million</td><td>5 million</td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Layer 2 Base Fee</td><td>-</td><td>to be added</td><td>to be added</td><td>to be added</td><td>to be added</td><td>to be added</td><td>to be added</td></tr><tr><td>Sequencing Frequency</td><td>-</td><td>0.5 - 2 minutes</td><td>0.5 - 2 minutes</td><td>0.5 - 2 minutes</td><td>0.5 - 2 minutes</td><td>~4-8 minutes</td><td>~6-15 minutes</td></tr><tr><td>Finality</td><td>12-13 minutes</td><td>7 days</td><td>7 days</td><td>8 - 32 hours</td><td>7 days</td><td>~1 hour</td><td>24 hours</td></tr></tbody></table>

###
