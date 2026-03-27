---
description: Reference for the growthepie per-chain metric detail endpoint.
---

# Endpoint: metrics/chains/{origin_key}/{metric_id}.json

`metrics/chains/{origin_key}/{metric_id}.json` returns a rich per-chain metric payload. This endpoint is the best choice when you need more than raw daily rows, such as rolling windows, weekly and monthly series, summary values, percentage changes, or optional hourly data.

## Request

```text
GET https://api.growthepie.com/v1/metrics/chains/{origin_key}/{metric_id}.json
```

Example:

```text
GET https://api.growthepie.com/v1/metrics/chains/arbitrum/txcount.json
```

## Key Response Sections

* `last_updated_utc`
* `details.metric_id`
* `details.metric_name`
* `details.timeseries`
* `details.changes`
* `details.summary`

## Example Response

```json
{
  "last_updated_utc": "2026-03-27 07:15:02",
  "details": {
    "metric_id": "txcount",
    "metric_name": "Transaction Count",
    "timeseries": {
      "daily": {
        "types": ["unix", "value"]
      },
      "hourly": {
        "types": ["unix", "value"]
      }
    },
    "changes": {
      "daily": {},
      "hourly": {}
    },
    "summary": {
      "last_1d": {
        "types": ["value"],
        "data": [2525170.0]
      }
    }
  }
}
```

## Time Granularity Behavior

* `daily` is the base time series
* `weekly`, `monthly`, and `quarterly` are available in richer metric payloads
* `hourly` is present only for metrics where `master.json.metrics.{metric_id}.hourly_available` is `true`

## When To Use metric detail

* You need daily plus higher-level rollups in one response
* You need summary fields such as `last_1d`, `last_7d`, or `last_30d`
* You are building a charting or analytics UI that mirrors the growthepie metric experience

## Caveats

* This endpoint uses `metric_id` in the path, not raw `metric_key`.
* Time-series rows in this endpoint typically use `unix` timestamps instead of `date` strings.

## Related Pages

* [What Is metric_key?](../core-concepts/what-is-metric-key.md)
* [Time Granularity, Freshness, And Update Cadence](../core-concepts/time-granularity-freshness-and-update-cadence.md)
