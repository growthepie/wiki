---
description: Learn what metric_key means in growthepie and how metric_key differs from metric_id.
---

# What Is metric_key?

`metric_key` is the canonical identifier for a raw exported series in growthepie data. You see `metric_key` values directly in flat export rows such as `txcount`, `daa`, `fees_paid_usd`, `fees_paid_eth`, or `gas_per_second`.

## Key Facts

* `metric_key` appears in flat row exports
* Some higher-level metrics map to one raw `metric_key`, such as `txcount`
* Some higher-level metrics map to multiple raw `metric_key` values, usually currency pairs such as USD and ETH
* `metric_key` is not the same thing as `metric_id`

## metric_id vs metric_key

| Term | Example | Used where |
| --- | --- | --- |
| `metric_id` | `fees` | Rich detail paths such as `metrics/chains/arbitrum/fees.json` |
| `metric_key` | `fees_paid_usd` | Flat row payloads such as `fundamentals.json` |

## Example

The higher-level metric `fees` maps to two raw `metric_key` values:

* `fees_paid_usd`
* `fees_paid_eth`

## FAQ

### Why do some metrics have both USD and ETH keys?

Currency-denominated metrics often expose both USD and ETH series in the backend metric registry and in `master.json`.

### Where do I find the mapping from `metric_id` to `metric_key`?

Use `master.json.metrics`. Each metric entry includes the canonical `metric_keys` array.

## Related Pages

* [Metric Reference Overview](../metric-reference/README.md)
* [Endpoint: master.json](../api-reference/master-json.md)
