---
description: Get the Arbitrum chain overview from growthepie and understand what it includes.
---

# How To Get Chain Overview Data For Arbitrum

Use the chain overview endpoint when you want the growthepie summary view for Arbitrum in one request. This is the right endpoint for highlights, rankings, KPI cards, achievements, and ecosystem context.

## Explore It Live

* Live platform: [https://www.growthepie.com/chains/arbitrum](https://www.growthepie.com/chains/arbitrum)

## API Path

* `https://api.growthepie.com/v1/chains/arbitrum/overview.json`

## Example Request

```bash
curl -s https://api.growthepie.com/v1/chains/arbitrum/overview.json
```

## What You Get

* `highlights`
* `events`
* `ranking`
* `kpi_cards`
* `achievements`
* `ecosystem`

## Caveats

* This is an overview payload, not a flat analytics export.
* Use metric detail endpoints when you need richer per-metric time series.

## Related Pages

* [Endpoint: chains/{origin_key}/overview.json](../api-reference/chain-overview-json.md)
* [Endpoint: metrics/chains/{origin_key}/{metric_id}.json](../api-reference/metric-detail-json.md)
