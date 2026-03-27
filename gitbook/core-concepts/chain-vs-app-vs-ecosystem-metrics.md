---
description: Understand the difference between chain metrics, app metrics, and ecosystem context in growthepie.
---

# Chain vs App vs Ecosystem Metrics

growthepie exposes multiple scopes of data. The most common public exports are chain-level metrics, but growthepie also exposes app coverage and richer chain overview JSON that includes ecosystem context such as top apps and active app counts.

## Key Facts

* Chain metrics answer questions about a chain such as `arbitrum` or `base`
* App coverage answers questions about projects and `owner_project` identifiers
* Ecosystem context appears in richer endpoints such as `chains/{origin_key}/overview.json`

## Scope Definitions

### Chain metrics

Chain metrics describe a covered chain. Examples include `txcount`, `daa`, `tvl`, and `throughput`.

### App metrics

App coverage is exposed through project metadata and app-related fields. The canonical public starting point is `labels/projects.json`.

### Ecosystem context

Ecosystem context combines chain-level and app-level information. For example, the chain overview endpoint includes `ecosystem.active_apps` and an `ecosystem.apps` table.

## Caveats

* Not every chain supports every metric. Use `master.json.chains.{origin_key}.supported_metrics`.
* Not every app-oriented or internal endpoint is public. This docs set only documents public endpoints that are currently accessible.

## Related Pages

* [Projects And owner_project](../entity-coverage-reference/projects-and-owner-project.md)
* [Endpoint: chains/{origin_key}/overview.json](../api-reference/chain-overview-json.md)
