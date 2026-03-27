---
description: Definition and usage guidance for the growthepie profit metric.
---

# profit

`profit` is the public growthepie metric identifier for Onchain Profit. Use `profit` when you want growthepie's net-like business metric rather than a gross fee series.

## Key Facts

* Canonical `metric_id`: `profit`
* Canonical `metric_key` values: `profit_usd`, `profit_eth`
* Unit: USD and ETH
* Hourly detail available: no
* Coverage: see `master.json.metrics.profit.supported_chains`
* Common search synonyms: onchain profit, net revenue

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/profit.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "profit_usd",
    "origin_key": "base",
    "date": "2026-03-01",
    "value": 126430.91
  },
  {
    "metric_key": "profit_eth",
    "origin_key": "base",
    "date": "2026-03-01",
    "value": 41.22
  }
]
```

## When To Use profit

* Compare the chain business outcome after cost-sensitive adjustments
* Pair with `fees` and `rent_paid` in chain economics analysis

## When Not To Use profit

* You need gross fees paid by users
* You need transaction or address activity

## Caveats

* `profit` is a derived business metric, not a raw activity count.
* In the backend metric registry, this metric is configured with missing-date fill behavior in some derived views.

## Related Pages

* [fees](fees.md)
* [rent_paid](rent-paid.md)
