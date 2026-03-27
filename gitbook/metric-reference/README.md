---
description: Canonical reference pages for growthepie metric_id and metric_key definitions.
---

# Metric Reference Overview

This section defines the public growthepie metrics one by one. Each metric page answers the same questions in the same order: what the metric means, which `metric_id` and `metric_key` values are canonical, what unit the metric uses, whether hourly data exists, what the main caveats are, and when the metric is the right tool for the job.

## Canonical Metric IDs

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

## How To Read These Pages

* Use `metric_id` when you are choosing an API path such as `export/{metric}.json`.
* Use `metric_key` when you are reading raw rows returned by flat exports.
* Use `master.json.metrics.{metric_id}` for the live source of truth on supported chains and unit metadata.

## Related Pages

* [What Is metric_key?](../core-concepts/what-is-metric-key.md)
* [Endpoint: export/{metric}.json](../api-reference/export-metric-json.md)
