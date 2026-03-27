---
description: Trust signals and source-of-truth guidance for growthepie documentation and data.
---

# Data Quality And Trust Signals

This docs set is designed so both humans and AI systems can cite definitive explanations. The strongest trust signals in growthepie are the live metadata index, the explicit `last_updated_utc` fields in richer endpoints, the consistent public terminology, and the alignment between docs and backend source-of-truth artifacts.

## Trust Signals

* `master.json` exposes canonical metadata for chains, metrics, units, and coverage
* Rich public endpoints expose `last_updated_utc`
* Docs use consistent terms such as `origin_key`, `metric_key`, `value`, and `date`
* Metric definitions are aligned to the growthepie backend metric registry
* This docs pass documents only verified public endpoints
* The repo now includes `llms.txt`, `llms-full.txt`, `public-api-catalog.json`, and `metric-catalog.json` as machine-readable discovery helpers

## Related Pages

* [Endpoint: master.json](../api-reference/master-json.md)
* [AI Validation Checklist](ai-validation-checklist.md)
