---
description: Definition and usage guidance for the growthepie daa metric.
---

# daa

`daa` measures active addresses for a covered chain. Use `daa` when you want an address-level activity proxy rather than a pure transaction count.

## Key Facts

* Canonical `metric_id`: `daa`
* Canonical `metric_key`: `daa`
* Unit: count
* Hourly detail available: yes
* Coverage: see `master.json.metrics.daa.supported_chains`
* Common search synonyms: daily active addresses, active addresses

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/daa.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "daa",
    "origin_key": "arbitrum",
    "date": "2026-01-01",
    "value": 907687.0
  }
]
```

## When To Use daa

* Compare address activity across chains
* Track user-like activity trends over time
* Complement `txcount` with an address-based signal

## When Not To Use daa

* You need exact unique users
* You need transaction volume or fee volume

## Caveats

* Address count is not the same thing as person count.
* Monthly aggregation for `daa` is not the same as summing daily values.

## Related Pages

* [txcount](txcount.md)
* [Metric Interpretation Caveats](../methodology-and-caveats/metric-interpretation-caveats.md)
