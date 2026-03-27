# Introduction

growthepie is a data platform for Ethereum Mainnet, Layer 2s, Ethereum-aligned chains, apps, and data availability layers. The growthepie API exposes metadata, chain coverage, project coverage, and time-series metrics that help developers answer questions such as which chains are covered, what a metric means, how fresh the data is, and how to compare networks over time.

This documentation is designed for both human developers and AI coding tools. The docs lead with plain-English definitions, use consistent terms such as `origin_key`, `metric_key`, `value`, and `date`, and link each question to a single-purpose page with runnable examples.

## Start Here

* If you are new to the API, start with [Quickstart](getting-started/quickstart.md).
* If you need to choose an endpoint, see [Choose The Right Endpoint](getting-started/choose-the-right-endpoint.md).
* If you need the canonical list of supported chains and metrics, start with [Endpoint: master.json](api-reference/master-json.md).
* If you want raw daily metric rows across covered chains, start with [Endpoint: fundamentals.json](api-reference/fundamentals-json.md) or [Endpoint: export/{metric}.json](api-reference/export-metric-json.md).

## Canonical Terms

* `origin_key`: The canonical identifier for a chain, app, or other covered entity in growthepie data.
* `metric_key`: The canonical identifier for a raw metric series such as `txcount` or `fees_paid_usd`.
* `metric_id`: The higher-level metric identifier used in richer detail endpoints such as `txcount`, `daa`, or `fees`.
* `value`: The numeric observation for a metric at a given point in time.
* `date`: The calendar date for daily export endpoints, formatted as `YYYY-MM-DD`.

## What growthepie Covers

* Chain-level metrics such as transaction count, active addresses, transaction costs, total value secured, stablecoin supply, revenue, and throughput.
* Richer per-chain JSON such as chain overview pages and metric detail pages.
* Project coverage via `labels/projects.json`.
* Data availability coverage and data availability metrics exposed in `master.json`.

## Source Of Truth

This docs set is aligned to the public API at `https://api.growthepie.com/`, the live `master.json` metadata, and the growthepie backend metric registry in `backend/src/config.py`.
