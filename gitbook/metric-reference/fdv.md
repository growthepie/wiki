---
description: Definition and usage guidance for the growthepie fdv metric.
---

# fdv

`fdv` measures Fully Diluted Valuation. Use `fdv` when you want a token valuation metric rather than a usage or onchain business metric.

## Key Facts

* Canonical `metric_id`: `fdv`
* Canonical `metric_key` values: `fdv_usd`, `fdv_eth`
* Unit: USD and ETH
* Hourly detail available: no
* Coverage: see `master.json.metrics.fdv.supported_chains`
* Common search synonyms: fully diluted valuation

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/fdv.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "fdv_usd",
    "origin_key": "arbitrum",
    "date": "2026-03-01",
    "value": 14500000000.0
  },
  {
    "metric_key": "fdv_eth",
    "origin_key": "arbitrum",
    "date": "2026-03-01",
    "value": 4850000.0
  }
]
```

## When To Use fdv

* Compare token valuation across covered chains
* Pair valuation analysis with onchain usage metrics

## When Not To Use fdv

* You need network activity
* You need market cap instead of fully diluted valuation

## Caveats

* `fdv` is a market metric and can move with price even when onchain usage is unchanged.

## Related Pages

* [market_cap](market-cap.md)
* [txcount](txcount.md)
