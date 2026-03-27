---
description: Reference for the growthepie export/{metric}.json endpoint family.
---

# Endpoint: export/{metric}.json

`export/{metric}.json` returns the flat public export for one fundamental metric across covered chains. Use `export/{metric}.json` when you want a single metric such as `txcount`, `daa`, or `fees` without downloading the broader `fundamentals.json` file.

## Request

```text
GET https://api.growthepie.com/v1/export/{metric}.json
```

Example:

```text
GET https://api.growthepie.com/v1/export/txcount.json
```

## Supported Public Metric Paths

* `app_revenue`
* `daa`
* `fdv`
* `fees`
* `market_cap`
* `profit`
* `rent_paid`
* `stables_mcap`
* `throughput`
* `tvl`
* `txcosts`
* `txcount`

## Example Response

```json
[
  {
    "metric_key": "txcount",
    "origin_key": "arbitrum",
    "date": "2021-05-29",
    "value": 9.0
  }
]
```

## Notes On metric vs metric_key

The path uses a higher-level metric identifier such as `fees` or `tvl`. The returned rows use raw `metric_key` values such as `fees_paid_usd`, `fees_paid_eth`, `tvl`, or `tvl_eth`.

## When To Use export/{metric}.json

* You want full metric history
* You want one metric across many chains
* You want a flat export for notebooks, CSV export, or a local cache

## Caveats

* The path parameter is the public metric identifier, not the raw `metric_key`.
* Multi-currency metrics can return more than one `metric_key` in the same file (usually USD and ETH).

## Related Pages

* [Metric Reference Overview](../metric-reference/README.md)
* [Fetch A Metric In curl](../recipes/fetch-a-metric-in-curl.md)
