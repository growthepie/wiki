---
description: Definition and usage guidance for the growthepie tvl metric.
---

# tvl

`tvl` is the growthepie metric identifier for Total Value Secured. Use `tvl` when you want the amount of value secured on a covered chain, expressed through paired USD and ETH raw series.

## Key Facts

* Canonical `metric_id`: `tvl`
* Canonical `metric_key` values: `tvl`, `tvl_eth`
* Unit: USD and ETH
* Hourly detail available: no
* Coverage: see `master.json.metrics.tvl.supported_chains`
* Common search synonyms: TVL, TVS, total value secured

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/tvl.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "tvl",
    "origin_key": "arbitrum",
    "date": "2026-03-01",
    "value": 2450000000.0
  },
  {
    "metric_key": "tvl_eth",
    "origin_key": "arbitrum",
    "date": "2026-03-01",
    "value": 820000.0
  }
]
```

## When To Use tvl

* Compare secured value across chains
* Track value concentration over time

## When Not To Use tvl

* You need transaction activity
* You need stablecoin-only coverage instead of broader secured value

## Caveats

* `tvl` and `tvl_eth` are separate raw series.
* Value metrics can move because of price changes, not just capital movement.

## Related Pages

* [stables_mcap](stables-mcap.md)
* [market_cap](market-cap.md)
