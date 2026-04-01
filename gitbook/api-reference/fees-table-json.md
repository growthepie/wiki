---
description: Reference for the growthepie fees/table.json endpoint.
---

# Endpoint: fees/table.json

`fees/table.json` is the public cross-chain fee table endpoint. It returns per-chain hourly series for the latest transaction-cost style metrics used in the growthepie fee comparison table, which makes it a good fit when you want the latest cost snapshot across supported chains.

## Request

```text
GET https://api.growthepie.com/v1/fees/table.json
```

## Key Facts

* Auth: not required
* Response type: object keyed by `chain_data`
* First-level keys under `chain_data`: one object per `origin_key`
* Current section structure: each chain exposes `hourly`
* Last verified in this docs refresh: April 1, 2026
* Live covered chains at that time: 14

## Current Hourly Metrics

The live payload currently exposes these hourly metrics per chain:

* `txcosts_median`
* `txcosts_native_median`
* `txcosts_avg`
* `txcosts_swap`
* `tps`
* `throughput`

For fee and cost series, rows use:

* `unix`
* `value_eth`
* `value_usd`
* `normalized`

For `tps` and `throughput`, rows use:

* `unix`
* `value`
* `normalized`

## Example Response

```json
{
  "chain_data": {
    "arbitrum": {
      "hourly": {
        "txcosts_median": {
          "types": ["unix", "value_eth", "value_usd", "normalized"],
          "data": [
            [1775037600000, 0.00000149534307, 0.0031, 0.37],
            [1775034000000, 0.00000125168, 0.0026, 0.24]
          ]
        },
        "tps": {
          "types": ["unix", "value", "normalized"],
          "data": [
            [1775037600000, 18.63083333333333, 0.9],
            [1775034000000, 19.433333333333334, 0.87]
          ]
        }
      }
    }
  }
}
```

## When To Use fees/table.json

* You want the latest cross-chain transaction-cost view
* You want hourly fee-table style data for supported chains in one request
* You want both ETH-denominated and USD-denominated transaction cost values

## When Not To Use fees/table.json

* You need full daily history for one metric
* You need the richer summary structure from `metrics/chains/{origin_key}/{metric_id}.json`
* You need project or app-level data

## Caveats

* `fees/table.json` is not a flat export endpoint.
* The payload is optimized for chain comparison UI and includes normalized values in addition to raw values.
* Despite the path name, the live payload currently includes `tps` and `throughput` alongside transaction-cost metrics.
* Coverage can change over time, so do not hardcode the current chain list.

## Related Pages

* [txcosts](../metric-reference/txcosts.md)
* [fees](../metric-reference/fees.md)
* [Endpoint: export/{metric}.json](export-metric-json.md)
* [Endpoint: metrics/chains/{origin_key}/{metric_id}.json](metric-detail-json.md)
