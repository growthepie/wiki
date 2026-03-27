---
description: Definition and usage guidance for the growthepie market_cap metric.
---

# market_cap

`market_cap` measures market capitalization for covered chains with supported token coverage. Use `market_cap` when you want circulating-value style valuation rather than fully diluted valuation.

## Key Facts

* Canonical `metric_id`: `market_cap`
* Canonical `metric_key` values: `market_cap_usd`, `market_cap_eth`
* Unit: USD and ETH
* Hourly detail available: no
* Coverage: see `master.json.metrics.market_cap.supported_chains`
* Common search synonyms: market cap

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/market_cap.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "market_cap_usd",
    "origin_key": "optimism",
    "date": "2026-03-01",
    "value": 6200000000.0
  },
  {
    "metric_key": "market_cap_eth",
    "origin_key": "optimism",
    "date": "2026-03-01",
    "value": 2070000.0
  }
]
```

## When To Use market_cap

* Compare token market value across covered chains
* Pair market value with usage metrics such as `txcount` or `daa`

## When Not To Use market_cap

* You need fully diluted valuation
* You need onchain activity or cost metrics

## Caveats

* `market_cap` is a market metric and can change because of price moves.

## Related Pages

* [fdv](fdv.md)
* [daa](daa.md)
