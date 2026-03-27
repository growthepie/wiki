---
description: >-
  Use this page to understand the growthepie API base URL, public endpoint
  families, response conventions, and the fastest path to the right JSON file.
---

# API Overview

The growthepie API is a public JSON API rooted at `https://api.growthepie.com/`. The fastest way to work with the API is to start with `master.json` for metadata, use `fundamentals.json` or `export/{metric}.json` for flat daily rows, and use the richer `chains/.../overview.json`, `metrics/.../{metric_id}.json`, or `apps/details/{owner_project}.json` endpoints when you need summaries, rankings, rolling windows, or multi-granularity time series.

The API currently exposes JSON files rather than a published OpenAPI specification. That means the canonical source of truth for supported chains, metrics, units, and coverage is `master.json`, plus the backend metric registry mirrored in the docs on this site.

## Base URL

```text
https://api.growthepie.com/
```

## Authentication

No authentication is required for the public endpoints documented in this site.

## Rate Limits

* Public usage guidance: do not make more than 10 API calls per minute.
* If you are building an AI agent, prefer fewer broader requests such as `master.json` plus one targeted detail endpoint instead of many repeated discovery calls.

## Response Conventions

* Flat export endpoints such as `fundamentals.json` and `export/{metric}.json` return arrays of rows with `metric_key`, `origin_key`, `date`, and `value`.
* Richer detail endpoints such as `chains/{origin_key}/overview.json`, `metrics/chains/{origin_key}/{metric_id}.json`, and `apps/details/{owner_project}.json` return objects with `last_updated_utc` and nested structured payloads.
* Daily export endpoints use `date` values formatted as `YYYY-MM-DD`.
* Richer time-series endpoints often use `unix` timestamps in milliseconds instead of `date` strings.
* Project-level endpoints use `owner_project` as the canonical project identifier.

## Public Endpoint Families

| Endpoint | Use when | Returns |
| --- | --- | --- |
| `v1/master.json` | You need metadata and coverage | Chains, metrics, DA layers, sources, and canonical metadata |
| `v1/fundamentals.json` | You need a broad daily export | Flat daily rows for supported fundamental metrics in the last 90 days |
| `v1/export/{metric}.json` | You need one metric across all covered chains | Flat daily rows for a single fundamental metric |
| `v1/chains/{origin_key}/overview.json` | You need chain summaries | Highlights, events, rankings, KPI cards, achievements, and ecosystem context |
| `v1/metrics/chains/{origin_key}/{metric_id}.json` | You need a rich metric detail page | Daily, weekly, monthly, quarterly, and optional hourly time series plus summary values |
| `v1/labels/projects.json` | You need project coverage | Project metadata as a typed table |
| `v1/apps/details/{owner_project}.json` | You need app or project detail | Project-level metrics, KPI cards, first-seen dates, chain breakdowns, and contracts tables |

## Stale Data Guardrail

Check `master.json` before trusting a chain in production workflows. If a chain entry has `deployment` or `deployment_flag` set to `DEV` or `ARCHIVED`, treat that chain as stale and exclude it from production analysis.

## Example Request

```bash
curl -s https://api.growthepie.com/v1/master.json
```

## FAQ

### Which endpoint should I start with?

Start with `master.json`. `master.json` tells you which `origin_key` values and `metric_id` values are supported before you query a narrower endpoint.

### How do I fetch app-level details for one project?

Use `apps/details/{owner_project}.json`. The `owner_project` list comes from `labels/projects.json`.

### Is there a published OpenAPI spec?

Not at the moment. This docs set documents the current public JSON surface directly from the live API and backend source of truth.

### Should I use `metric_id` or `metric_key`?

Use `metric_id` when the endpoint path expects a higher-level metric such as `txcount` or `fees`. Use `metric_key` when you are reading raw exported rows such as `fees_paid_usd`.

## Related Pages

* [Quickstart](getting-started/quickstart.md)
* [Endpoint: master.json](api-reference/master-json.md)
* [Endpoint: fundamentals.json](api-reference/fundamentals-json.md)
* [Endpoint: metrics/chains/{origin_key}/{metric_id}.json](api-reference/metric-detail-json.md)
* [Endpoint: apps/details/{owner_project}.json](api-reference/app-detail-json.md)
