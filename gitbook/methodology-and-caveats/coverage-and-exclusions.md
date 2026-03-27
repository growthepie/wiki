---
description: Coverage rules and exclusions in growthepie data.
---

# Coverage And Exclusions

Coverage in growthepie is metric-specific and chain-specific. A chain can be present in `master.json` but still exclude a specific metric, so consumers should always check both the chain coverage and the metric coverage metadata.

## Key Facts

* Check `master.json.chains.{origin_key}.supported_metrics`
* Check `master.json.metrics.{metric_id}.supported_chains`
* The live API changes over time, so prefer metadata over hardcoded lists

## Practical Guidance

* Validate `origin_key` before querying a metric detail endpoint
* Validate `metric_id` before generating API code or client stubs
* Treat legacy or inaccessible endpoints as unsupported until verified publicly

## Related Pages

* [Supported Chains And origin_key](../entity-coverage-reference/supported-chains-and-origin-key.md)
* [Endpoint: master.json](../api-reference/master-json.md)
