---
description: Choose the correct growthepie endpoint based on the developer task you need to solve.
---

# Choose The Right Endpoint

Different growthepie endpoints answer different developer intents. This page maps each common task to the correct endpoint so you can retrieve the narrowest correct JSON file instead of starting from a broad export and filtering everything yourself.

## Endpoint Selector

| If your question is... | Use this endpoint | Why |
| --- | --- | --- |
| Which chains and metrics are supported? | `v1/master.json` | `master.json` is the canonical metadata index |
| What are the last 90 days of fundamental metrics across covered chains? | `v1/fundamentals.json` | Returns flat daily rows for many metrics together |
| What is the full history for one metric such as `txcount`? | `v1/export/{metric}.json` | Returns flat rows for one fundamental metric across chains |
| What does the chain overview for `arbitrum` look like? | `v1/chains/arbitrum/overview.json` | Returns highlights, events, rankings, KPI cards, and ecosystem context |
| What is the rich metric detail view for `txcount` on `arbitrum`? | `v1/metrics/chains/arbitrum/txcount.json` | Returns multiple time granularities, changes, and summary values |
| Which apps or projects are covered? | `v1/labels/projects.json` | Returns project coverage metadata |
| Which projects have actual datapoints and can be used with app details? | `v1/labels/projects_filtered.json` | Returns the subset of projects with real datapoints such as `txcount` |
| What does the project detail page for `uniswap` look like? | `v1/apps/details/uniswap.json` | Returns project-level metrics, KPI cards, first-seen dates, and contracts tables |

## Rule Of Thumb

* Start with `master.json` if you need discovery.
* Use flat exports if you want rows that load cleanly into spreadsheets, pandas, SQL, or notebooks.
* Use richer detail endpoints if you want pre-aggregated summaries, rankings, rolling windows, multiple time granularities, or project-level breakdowns.

## Caveats

* `fundamentals.json` is intentionally limited to the last 90 days.
* `export/{metric}.json` is only available for public fundamental metrics.
* Some legacy or internal-looking paths exist in backend code but are not public or not consistently accessible. This docs set only covers verified public endpoints.

## Related Pages

* [API Overview](../api.md)
* [Endpoint: fundamentals.json](../api-reference/fundamentals-json.md)
* [Endpoint: metrics/chains/{origin_key}/{metric_id}.json](../api-reference/metric-detail-json.md)
