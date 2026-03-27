---
description: Fetch app-level metrics for Uniswap with growthepie and the app detail endpoint.
---

# How To Fetch App-Level Metrics For Uniswap

Use `apps/details/uniswap.json` when you want a project-level response for Uniswap with metrics, KPI cards, first-seen dates, and contract tables. This is the fastest public path to a grounded app-level payload in the growthepie API.

## Explore It Live

* Live platform: [https://www.growthepie.com/](https://www.growthepie.com/)

## API Path

* `https://api.growthepie.com/v1/apps/details/uniswap.json`

## Example Request

```bash
curl -s https://api.growthepie.com/v1/apps/details/uniswap.json
```

## Example Response Shape

```json
{
  "last_updated_utc": "2026-03-27 05:40:34",
  "metrics": {
    "txcount": {
      "metric_name": "Transaction Count",
      "avg": true
    }
  },
  "first_seen": {
    "ethereum": "2021-01-01"
  }
}
```

## Caveats

* Validate `uniswap` against `labels/projects_filtered.json` before assuming the endpoint exists.
* The metric set can vary by project.

## Related Pages

* [Endpoint: apps/details/{owner_project}.json](../api-reference/app-detail-json.md)
* [How To Use projects_filtered.json](how-to-use-projects-filtered-json.md)
