---
description: Reference for growthepie data availability layer coverage and DA metric identifiers.
---

# Data Availability Layers And DA Metrics

growthepie exposes data availability layer coverage through `master.json.da_layers` and data availability metric coverage through `master.json.da_metrics`. During this docs refresh on March 27, 2026, the live API exposed four DA layers and five DA metrics.

## Current DA Layers

* `da_celestia`: Celestia
* `da_eigenda`: EigenDA
* `da_ethereum_blobs`: Ethereum Blobs
* `da_ethereum_calldata`: Ethereum Calldata

## Current DA Metrics

* `blob_count`
* `blob_producers`
* `data_posted`
* `fees_paid`
* `fees_per_mbyte`

## Related Pages

* [Endpoint: master.json](../api-reference/master-json.md)
* [Coverage And Exclusions](../methodology-and-caveats/coverage-and-exclusions.md)
