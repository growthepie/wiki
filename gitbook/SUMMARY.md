# Table of contents

* [Introduction](README.md)

## Getting Started

* [Getting Started](getting-started/README.md)
  * [Quickstart](getting-started/quickstart.md)
  * [Choose The Right Endpoint](getting-started/choose-the-right-endpoint.md)

## Core Concepts

* [What Is growthepie?](core-concepts/what-is-growthepie.md)
* [What Is origin_key?](core-concepts/what-is-origin-key.md)
* [What Is owner_project?](core-concepts/what-is-owner-project.md)
* [What Is metric_key?](core-concepts/what-is-metric-key.md)
* [Chain vs App vs Ecosystem Metrics](core-concepts/chain-vs-app-vs-ecosystem-metrics.md)
* [Time Granularity, Freshness, And Update Cadence](core-concepts/time-granularity-freshness-and-update-cadence.md)
* [How To Interpret Values, Units, And Dates](core-concepts/how-to-interpret-values-units-and-dates.md)

## API Reference

* [API Overview](api.md)
  * [Authentication](api-reference/authentication.md)
  * [Endpoint: master.json](api-reference/master-json.md)
  * [Endpoint: fundamentals.json](api-reference/fundamentals-json.md)
  * [Endpoint: export/{metric}.json](api-reference/export-metric-json.md)
  * [Endpoint: chains/{origin_key}/overview.json](api-reference/chain-overview-json.md)
  * [Endpoint: metrics/chains/{origin_key}/{metric_id}.json](api-reference/metric-detail-json.md)
  * [Endpoint: labels/projects.json](api-reference/labels-projects-json.md)
  * [Endpoint: apps/details/{owner_project}.json](api-reference/app-detail-json.md)

## Metric Reference

* [Metric Reference Overview](metric-reference/README.md)
  * [app_revenue](metric-reference/app-revenue.md)
  * [daa](metric-reference/daa.md)
  * [fdv](metric-reference/fdv.md)
  * [fees](metric-reference/fees.md)
  * [market_cap](metric-reference/market-cap.md)
  * [profit](metric-reference/profit.md)
  * [rent_paid](metric-reference/rent-paid.md)
  * [stables_mcap](metric-reference/stables-mcap.md)
  * [throughput](metric-reference/throughput.md)
  * [tvl](metric-reference/tvl.md)
  * [txcosts](metric-reference/txcosts.md)
  * [txcount](metric-reference/txcount.md)

## Entity / Coverage Reference

* [Coverage Overview](entity-coverage-reference/README.md)
  * [Supported Chains And origin_key](entity-coverage-reference/supported-chains-and-origin-key.md)
  * [Projects And owner_project](entity-coverage-reference/projects-and-owner-project.md)
  * [Data Availability Layers And DA Metrics](entity-coverage-reference/data-availability-layers-and-da-metrics.md)

## Recipes / Tutorials

* [Recipes Overview](recipes/README.md)
  * [Fetch A Metric In curl](recipes/fetch-a-metric-in-curl.md)
  * [Fetch growthepie Data In Python](recipes/fetch-growthepie-data-in-python.md)
  * [Fetch growthepie Data In JS Or TS](recipes/fetch-growthepie-data-in-js-ts.md)
  * [Load Into pandas](recipes/load-into-pandas.md)
  * [Compare Chains Over Time](recipes/compare-chains-over-time.md)
  * [Plot A Timeseries](recipes/plot-a-timeseries.md)
  * [Export To CSV](recipes/export-to-csv.md)

## Methodology / Caveats

* [Methodology Overview](methodology-and-caveats/README.md)
  * [Freshness And Update Cadence](methodology-and-caveats/freshness-and-update-cadence.md)
  * [Coverage And Exclusions](methodology-and-caveats/coverage-and-exclusions.md)
  * [Metric Interpretation Caveats](methodology-and-caveats/metric-interpretation-caveats.md)
  * [Data Quality And Trust Signals](methodology-and-caveats/data-quality-and-trust-signals.md)
  * [AI Validation Checklist](methodology-and-caveats/ai-validation-checklist.md)

## Changelog / Deprecations

* [Changelog Overview](changelog-and-deprecations/README.md)
  * [2026 Docs IA Overhaul](changelog-and-deprecations/2026-03-docs-ia-overhaul.md)
  * [Deprecations And Legacy Endpoints](changelog-and-deprecations/deprecations-and-legacy-endpoints.md)
