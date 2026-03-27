---
description: Start here if you are new to growthepie and want to make the first correct API request quickly.
---

# Getting Started

The fastest path into the growthepie API is to learn three terms first: `origin_key`, `metric_id`, and `metric_key`. Once you know those three terms, you can choose the right endpoint for metadata, flat exports, or richer detail JSON without guessing.

## In One Minute

1. Fetch `master.json` to discover supported chains, metrics, and metadata.
2. Use `fundamentals.json` if you want daily rows across many metrics and chains.
3. Use `export/{metric}.json` if you want one metric across all covered chains.
4. Use `metrics/chains/{origin_key}/{metric_id}.json` if you want a rich per-chain metric response with summaries and multiple time granularities.

## First Three Questions To Ask

### What chain or entity am I querying?

Use `origin_key`. Example: `arbitrum`, `base`, `ethereum`, or `zksync_era`.

### What higher-level metric am I querying?

Use `metric_id`. Example: `txcount`, `daa`, `fees`, or `throughput`.

### What raw series key will I see in flat exports?

Use `metric_key`. Example: `txcount`, `daa`, `fees_paid_usd`, or `gas_per_second`.

## Recommended Reading Order

* [Quickstart](quickstart.md)
* [Choose The Right Endpoint](choose-the-right-endpoint.md)
* [What Is origin_key?](../core-concepts/what-is-origin-key.md)
* [What Is metric_key?](../core-concepts/what-is-metric-key.md)

## Related Pages

* [API Overview](../api.md)
* [Endpoint: master.json](../api-reference/master-json.md)
* [Metric Reference Overview](../metric-reference/README.md)
