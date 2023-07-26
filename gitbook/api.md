# API

Our API endpoint can be found at `https://api.growthepie.xyz/`

### Master endpoint

Contains info on all supported chains and metrics

```
v1/master.json
```

### Metrics endpoint

Returns the daily metric values for all chains and some additional information (e.g. 1d change).

* **Daily active addresses:** `v1/metrics/daa.json`
* **Transaction count:** `v1/metrics/txcount.json`
* **Transaction costs:** `v1/metrics/txcosts.json`
* **Total value locked:** `v1/metrics/tvl.json`
* **Fees paid by users:** `v1/metrics/fees.json`
* **Stablecoin market cap:** `v1/metrics/stables.json`

### Chains endpoint

Returns all metrics on daily granularity for the selected chain.

* **Ethereum:** `v1/chains/ethereum.json`
* **zkSync Era:** `v1/chains/zksync_era.json`
* **Arbitrum:** `v1/chains/arbitrum.json`
* **Optimism:** `v1/chains/optimism.json`
* **ImmutableX:** `v1/chains/imx.json`
* **Polygon zkEVM:** `v1/chains/polygon_zkevm.json`

