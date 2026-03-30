---
description: Understand the difference between chain metrics, app metrics, and ecosystem context in growthepie.
---

# Chain vs App vs Ecosystem Metrics

growthepie exposes multiple scopes of data. Chain metrics answer high-level network questions for one `origin_key`. Application metrics answer project questions for one `owner_project`, and those application metrics are mostly based on smart contracts mapped to that project.

## Key Facts

* Chain metrics answer questions about a chain such as `arbitrum` or `base`
* Application metrics answer questions about a project such as `uniswap`, `polymarket`, or `circlefin`.
* Application metrics are mostly based on smart contracts mapped to an `owner_project`
* Ecosystem context appears in richer endpoints such as `chains/{origin_key}/overview.json`

## Scope Definitions

### Chain metrics

Chain metrics describe a covered network. Chain metrics are the right scope when you want high-level information about usage, economics, or value on a chain.

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

### App metrics

App metrics describe one application or project. In growthepie, the public app scope is keyed by `owner_project`, and the metrics are mostly based on smart contracts mapped to that `owner_project`.

Common app metrics currently include:

* `txcount`
* `daa`
* `gas_fees`
* `success_rate`
* `token_price`
* `token_volume`
* `market_cap`

The canonical public starting points are `labels/projects.json` for project discovery, `labels/projects_filtered.json` for projects with actual datapoints, and `apps/details/{owner_project}.json` for project detail.

### Ecosystem context

Ecosystem context combines chain-level and app-level information. For example, the chain overview endpoint includes `ecosystem.active_apps` and an `ecosystem.apps` table.

## Caveats

* Not every chain supports every metric. Use `master.json.chains.{origin_key}.supported_metrics`.
* Not every app-oriented or internal endpoint is public. This docs set only documents public endpoints that are currently accessible.
* Not every chain metric exists at the application level.
* The application metric set can vary by `owner_project`.

## Related Pages

* [What Is owner_project?](what-is-owner-project.md)
* [Projects And owner_project](../entity-coverage-reference/projects-and-owner-project.md)
* [Endpoint: chains/{origin_key}/overview.json](../api-reference/chain-overview-json.md)
* [Endpoint: apps/details/{owner_project}.json](../api-reference/app-detail-json.md)
