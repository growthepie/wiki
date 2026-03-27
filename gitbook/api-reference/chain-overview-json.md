---
description: Reference for the growthepie chain overview endpoint.
---

# Endpoint: chains/{origin_key}/overview.json

`chains/{origin_key}/overview.json` returns a rich summary for one chain. This endpoint is the right choice when you want highlights, events, rankings, KPI cards, achievements, and ecosystem context in one response instead of reconstructing a chain profile yourself from flat exports.

## Request

```text
GET https://api.growthepie.com/v1/chains/{origin_key}/overview.json
```

Example:

```text
GET https://api.growthepie.com/v1/chains/arbitrum/overview.json
```

## Key Response Sections

* `last_updated_utc`
* `data.chain_id`
* `data.chain_name`
* `data.highlights`
* `data.events`
* `data.ranking`
* `data.kpi_cards`
* `data.achievements`
* `data.blockspace`
* `data.ecosystem`

## Example Response

```json
{
  "last_updated_utc": "2026-03-27 05:35:04",
  "data": {
    "chain_id": "arbitrum",
    "chain_name": "Arbitrum One",
    "highlights": [
      {
        "metric_id": "txcount",
        "metric_name": "Transaction Count",
        "type": "lifetime_level_up",
        "date": "2026-03-24"
      }
    ],
    "ecosystem": {
      "active_apps": {
        "7d": 0
      }
    }
  }
}
```

## When To Use chain overview

* You are building a chain summary page
* You need Ethereum ecosystem rankings and KPI cards
* You want chain context plus ecosystem context in one request

## Caveats

* This endpoint is structured for overview use cases, not raw analytics row exports.
* The available ranking and KPI card metrics depend on chain support and growthepie's chain configuration.

## Related Pages

* [What Is origin_key?](../core-concepts/what-is-origin-key.md)
* [Endpoint: metrics/chains/{origin_key}/{metric_id}.json](metric-detail-json.md)
