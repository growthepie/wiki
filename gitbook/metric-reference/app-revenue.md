---
description: Definition and usage guidance for the growthepie app_revenue metric.
---

# app_revenue

`app_revenue` measures App Revenue in growthepie's public metric model. Use `app_revenue` when you want app-oriented fee generation rather than chain-level fees paid by users.

## Key Facts

* Canonical `metric_id`: `app_revenue`
* Canonical `metric_key` values: `app_fees_usd`, `app_fees_eth`
* Unit: USD and ETH
* Hourly detail available: no
* Coverage: see `master.json.metrics.app_revenue.supported_chains`
* Common search synonyms: app fees, app revenue

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/app_revenue.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "app_fees_usd",
    "origin_key": "base",
    "date": "2026-03-01",
    "value": 51420.89
  },
  {
    "metric_key": "app_fees_eth",
    "origin_key": "base",
    "date": "2026-03-01",
    "value": 16.74
  }
]
```

## When To Use app_revenue

* Compare app-oriented fee generation across chains
* Separate app activity monetization from chain fee metrics

## When Not To Use app_revenue

* You need chain-level fees paid by users
* You need project coverage metadata rather than a metric export

## Caveats

* `app_revenue` is distinct from `fees`.
* Availability still depends on per-chain support in `master.json`.

## Related Pages

* [fees](fees.md)
* [Endpoint: labels/projects.json](../api-reference/labels-projects-json.md)
