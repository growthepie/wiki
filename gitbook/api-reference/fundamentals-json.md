---
description: Reference for the growthepie fundamentals.json endpoint.
---

# Endpoint: fundamentals.json

`fundamentals.json` is the broad daily export endpoint for public fundamental metrics. `fundamentals.json` returns flat rows with `metric_key`, `origin_key`, `date`, and `value` for covered chains, filtered to the last 90 days.

## Request

```text
GET https://api.growthepie.com/v1/fundamentals.json
```

## Key Facts

* Auth: not required
* Response type: array of flat rows
* Row fields: `metric_key`, `origin_key`, `date`, `value`
* Time window: last 90 days
* Notable inclusion: `aa_last7d` is included in the public fundamentals export

## Example Response

```json
[
  {
    "metric_key": "aa_last7d",
    "origin_key": "arbitrum",
    "date": "2026-01-01",
    "value": 907687.0
  },
  {
    "metric_key": "txcount",
    "origin_key": "arbitrum",
    "date": "2026-01-01",
    "value": 2525170.0
  }
]
```

## When To Use fundamentals.json

* You want many fundamental metrics in one file
* You want a flat daily export that loads well into spreadsheets, SQL, or pandas
* You only need the recent 90-day window

## When Not To Use fundamentals.json

* You need full history for one metric
* You need rich summary fields, rankings, or hourly time series
* You need project coverage metadata

## Caveats

* `fundamentals.json` is not full history.
* Currency-paired raw series that end in `_eth` are filtered out of this export.
* Coverage still depends on the chain and metric filtering defined in growthepie metadata.

## Related Pages

* [Endpoint: export/{metric}.json](export-metric-json.md)
* [Load Into pandas](../recipes/load-into-pandas.md)
