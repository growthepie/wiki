---
description: Learn how to interpret value, units, currencies, timestamps, and dates in growthepie responses.
---

# How To Interpret Values, Units, And Dates

The same numeric field name, `value`, is used across flat exports, but the unit behind `value` depends on the metric. You should always read `value` together with the endpoint, the `metric_key`, and the unit metadata from `master.json.metrics`.

## Key Facts

* `value` is numeric but not self-describing
* `date` is a daily string in flat exports
* Rich endpoints often use `unix` timestamps in milliseconds
* Currency metrics usually expose both USD and ETH `metric_key` values

## Common Unit Patterns

| Metric family | Example | Unit pattern |
| --- | --- | --- |
| Count | `txcount`, `daa` | Plain numeric value |
| USD / ETH pair | `fees`, `tvl`, `market_cap` | Separate USD and ETH raw series |
| Throughput | `gas_per_second` | `Mgas/s` |

## Example

```json
{
  "metric_key": "fees_paid_usd",
  "origin_key": "arbitrum",
  "date": "2026-03-01",
  "value": 123456.78
}
```

Interpretation:

* `metric_key` tells you this is the USD series for `fees`
* `origin_key` tells you the chain is `arbitrum`
* `date` is the daily observation date
* `value` is the numeric amount for that series and date

## Caveats

* Do not assume that all `value` fields are USD.
* Do not assume that all timestamps are `date` strings.
* Do not assume that monthly values are always sums. Monthly aggregation depends on the metric.

## Related Pages

* [What Is metric_key?](what-is-metric-key.md)
* [Metric Reference Overview](../metric-reference/README.md)
