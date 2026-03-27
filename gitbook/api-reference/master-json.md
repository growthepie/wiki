---
description: Reference for the growthepie master.json endpoint, the canonical metadata index for chains, metrics, and coverage.
---

# Endpoint: master.json

`master.json` is the canonical metadata index for the public growthepie API. `master.json` answers the core discovery questions directly: which chains are covered, which metrics are supported, what units each metric uses, which chains support each metric, which chains should be excluded because they are stale, and when the metadata was last updated.

## Request

```text
GET https://api.growthepie.com/v1/master.json
```

## Key Facts

* Auth: not required
* Best use case: discovery, metadata, coverage, and schema-aware clients
* Response type: object
* Includes: `chains`, `metrics`, `da_layers`, `da_metrics`, `sources`, `maturity_levels`, `last_updated_utc`
* Chain deployment safety field: `deployment` in the current live API, and `deployment_flag` if present on other environments

## Example Response

```json
{
  "current_version": "v1",
  "last_updated_utc": "2026-03-27 05:30:09",
  "chains": {
    "arbitrum": {
      "name": "Arbitrum One",
      "url_key": "arbitrum",
      "supported_metrics": [
        "tvl",
        "txcount",
        "daa",
        "stables_mcap",
        "fees",
        "rent_paid",
        "profit",
        "txcosts",
        "fdv",
        "market_cap",
        "throughput",
        "app_revenue"
      ]
    }
  },
  "metrics": {
    "txcount": {
      "name": "Transaction Count",
      "metric_keys": ["txcount"],
      "hourly_available": true
    }
  }
}
```

## When To Use master.json

* Before validating an `origin_key`
* Before validating a `metric_id`
* Before deciding whether a metric has hourly detail
* Before deciding whether a chain supports a given metric
* Before excluding stale chains whose `deployment` or `deployment_flag` is `DEV` or `ARCHIVED`

## FAQ

### Should I hardcode supported chains?

Prefer `master.json` over hardcoding. `master.json` is the intended machine-readable discovery file for chain and metric coverage.

### Where do I find the raw `metric_key` mapping?

Use `master.json.metrics.{metric_id}.metric_keys`.

### Which chains should I exclude because of stale data?

Exclude any chain whose `deployment` is `DEV` or `ARCHIVED`.

## Related Pages

* [What Is origin_key?](../core-concepts/what-is-origin-key.md)
* [What Is owner_project?](../core-concepts/what-is-owner-project.md)
* [What Is metric_key?](../core-concepts/what-is-metric-key.md)
* [Supported Chains And origin_key](../entity-coverage-reference/supported-chains-and-origin-key.md)
