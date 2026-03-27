---
description: Learn how growthepie uses daily, weekly, monthly, quarterly, and hourly data across endpoints.
---

# Time Granularity, Freshness, And Update Cadence

growthepie uses more than one time model. Flat exports such as `fundamentals.json` and `export/{metric}.json` are daily, while richer metric detail endpoints can include daily, weekly, monthly, quarterly, and for some metrics hourly time series.

## Key Facts

* Flat exports use daily rows with `date` formatted as `YYYY-MM-DD`
* Rich metric detail endpoints can expose `daily`, `weekly`, `monthly`, `quarterly`, and optional `hourly` series
* `fundamentals.json` is limited to the last 90 days
* Richer endpoints expose `last_updated_utc`

## How Freshness Works

* Use `last_updated_utc` when the response includes it
* Use the most recent `date` in a flat export when the response is a raw array
* Treat hourly series as available only when `master.json.metrics.{metric}.hourly_available` is `true`

## Example

`txcount` is a metric with hourly availability. The rich endpoint `metrics/chains/arbitrum/txcount.json` includes:

* `timeseries.daily`
* `timeseries.weekly`
* `timeseries.monthly`
* `timeseries.quarterly`
* `timeseries.hourly`

## FAQ

### Is `fundamentals.json` full history?

No. `fundamentals.json` is a rolling 90-day daily export.

### Where do I get full history for one metric?

Use `export/{metric}.json` for flat rows or `metrics/chains/{origin_key}/{metric_id}.json` for richer series per chain.

## Related Pages

* [Endpoint: fundamentals.json](../api-reference/fundamentals-json.md)
* [Endpoint: metrics/chains/{origin_key}/{metric_id}.json](../api-reference/metric-detail-json.md)
