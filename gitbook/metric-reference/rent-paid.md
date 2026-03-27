---
description: Definition and usage guidance for the growthepie rent_paid metric.
---

# rent_paid

`rent_paid` measures Rent Paid to L1. Use `rent_paid` when you want the cost side of a chain's relationship with the base layer rather than the gross fees paid by users.

## Key Facts

* Canonical `metric_id`: `rent_paid`
* Canonical `metric_key` values: `rent_paid_usd`, `rent_paid_eth`
* Unit: USD and ETH
* Hourly detail available: no
* Coverage: see `master.json.metrics.rent_paid.supported_chains`
* Common search synonyms: L1 rent, settlement cost

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/rent_paid.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "rent_paid_usd",
    "origin_key": "optimism",
    "date": "2026-03-01",
    "value": 84521.33
  },
  {
    "metric_key": "rent_paid_eth",
    "origin_key": "optimism",
    "date": "2026-03-01",
    "value": 27.58
  }
]
```

## When To Use rent_paid

* Compare L1-related cost burden across chains
* Pair cost-side analysis with `fees` and `profit`

## When Not To Use rent_paid

* You need gross user-paid fees
* You need app-level revenue

## Caveats

* `rent_paid` is not a usage metric.
* In the backend metric registry, this metric is configured with missing-date fill behavior in some derived views.

## Related Pages

* [fees](fees.md)
* [profit](profit.md)
