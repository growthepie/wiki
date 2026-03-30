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

## Availability Notice

The growthepie API is currently public. growthepie may change API access, packaging, or authentication requirements in the future, so production integrations should avoid assuming that the current access model is permanent.

## Rate Limits

* Public usage guidance: do not make more than 10 API calls per minute.
* If you are building an AI agent, prefer fewer broader requests such as `master.json` plus one targeted detail endpoint instead of many repeated discovery calls.

## Coverage And Data Packages

* Data is only available for chains that work with growthepie.
* Chain-level data belongs to the Basic package.
* Application-level data such as `apps/details/{owner_project}.json` belongs to the Advanced package.
* Commercial packaging details: [growthepie data tiers](https://www.growthepie.com/sales#data-tiers)

## Chain Metrics vs Application Metrics

Use chain metrics when the question is about a network such as `arbitrum`, `base`, or `ethereum`. Use application metrics when the question is about a smart-contract application mapped to an `owner_project` such as `uniswap`, `polymarket`, or `circlefin`.

### Chains

Chains are the high-level network entities in growthepie. Chain metrics describe network-wide activity, economics, and value for one `origin_key`.

Common chain metrics include:

* `txcount`
* `daa`
* `fees`
* `txcosts`
* `throughput`
* `tvl`
* `stables_mcap`
* `rent_paid`
* `profit`
* `market_cap`
* `fdv`

### Applications

Applications are smart contracts mapped to `owner_project` values. Application metrics are mostly derived from activity on those mapped contracts, and the public app-detail endpoint returns those metrics for one project at a time.

Common app metrics currently include:

* `txcount`
* `daa`
* `gas_fees`
* `success_rate`
* `token_price`
* `token_volume`
* `market_cap`

### Practical Rule

* If the identifier is `origin_key`, you are usually working with chain-level data.
* If the identifier is `owner_project`, you are usually working with application-level data.
* Not every chain metric has an application-level equivalent, and the app metric set can vary by project.

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
| `v1/labels/projects_filtered.json` | You need projects with real datapoints | Filtered project metadata for `owner_project` values that have actual activity such as `txcount` |
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

Use `apps/details/{owner_project}.json`. The safest discovery source is `labels/projects_filtered.json`, because the app detail endpoint is only available for `owner_project` values in that filtered subset.

### What should I do if I publish growthepie data?

Clearly state growthepie as the data source. If the usage is for research activity such as student or academic work, reach out if growthepie can support the work.

### Is there a published OpenAPI spec?

Not at the moment. This docs set documents the current public JSON surface directly from the live API and backend source of truth.

### Will the API always stay public?

Not necessarily. The API is currently public, but growthepie may change access or authentication requirements in the future.

### Should I use `metric_id` or `metric_key`?

Use `metric_id` when the endpoint path expects a higher-level metric such as `txcount` or `fees`. Use `metric_key` when you are reading raw exported rows such as `fees_paid_usd`.

## Related Pages

* [Quickstart](getting-started/quickstart.md)
* [Chain vs App vs Ecosystem Metrics](core-concepts/chain-vs-app-vs-ecosystem-metrics.md)
* [Endpoint: master.json](api-reference/master-json.md)
* [Endpoint: fundamentals.json](api-reference/fundamentals-json.md)
* [Endpoint: metrics/chains/{origin_key}/{metric_id}.json](api-reference/metric-detail-json.md)
* [Endpoint: labels/projects_filtered.json](api-reference/labels-projects-filtered-json.md)
* [Endpoint: apps/details/{owner_project}.json](api-reference/app-detail-json.md)
* [Usage Rules And Data Tiers](methodology-and-caveats/usage-rules-and-data-tiers.md)
