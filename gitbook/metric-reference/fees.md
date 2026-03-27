---
description: Definition and usage guidance for the growthepie fees metric.
---

# fees

`fees` is the public growthepie metric identifier for fees paid by users. In the growthepie metadata, this metric is also labeled `Revenue`, so you should treat `fees` and revenue as the same canonical public metric in API paths and docs.

## Key Facts

* Canonical `metric_id`: `fees`
* Canonical `metric_key` values: `fees_paid_usd`, `fees_paid_eth`
* Unit: USD and ETH
* Hourly detail available: yes
* Coverage: see `master.json.metrics.fees.supported_chains`
* Common search synonyms: revenue, fees paid by users

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/fees.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "fees_paid_usd",
    "origin_key": "arbitrum",
    "date": "2026-03-01",
    "value": 315245.11
  },
  {
    "metric_key": "fees_paid_eth",
    "origin_key": "arbitrum",
    "date": "2026-03-01",
    "value": 102.74
  }
]
```

## When To Use fees

* Measure the fee volume users paid on a chain
* Compare chain fee generation over time

## When Not To Use fees

* You need net profit instead of gross user-paid fees
* You need app-specific fee volume instead of chain-level fees

## Caveats

* The API path uses `fees`, while the metadata display name is `Revenue`.
* `fees` is distinct from `app_revenue`.

## Related Pages

* [app_revenue](app-revenue.md)
* [profit](profit.md)
