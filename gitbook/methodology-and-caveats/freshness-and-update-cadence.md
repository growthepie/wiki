---
description: How to understand data freshness and update cadence in growthepie.
---

# Freshness And Update Cadence

growthepie exposes freshness in two main ways. Rich endpoints expose `last_updated_utc`, while flat daily exports expose the newest available `date` row.

## Key Facts

* `master.json` exposes `last_updated_utc`
* Rich chain and metric detail endpoints expose `last_updated_utc`
* `fundamentals.json` is a rolling 90-day daily export
* Hourly detail exists only for metrics marked `hourly_available: true` in `master.json`

## Practical Guidance

* Read `last_updated_utc` before caching a rich endpoint
* Inspect the most recent `date` before assuming a flat export includes the current day
* Do not assume every metric has hourly detail

## Related Pages

* [Time Granularity, Freshness, And Update Cadence](../core-concepts/time-granularity-freshness-and-update-cadence.md)
* [Endpoint: metrics/chains/{origin_key}/{metric_id}.json](../api-reference/metric-detail-json.md)
