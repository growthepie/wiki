---
description: Reference for the growthepie apps/details/{owner_project}.json endpoint.
---

# Endpoint: apps/details/{owner_project}.json

`apps/details/{owner_project}.json` returns a rich project-level response for a covered app whose contracts have mapped activity. Use `apps/details/{owner_project}.json` when you need app-level metrics, KPI cards, first-seen dates by chain, chain-by-chain time series, and contracts tables for one `owner_project`.

## Request

```text
GET https://api.growthepie.com/v1/apps/details/{owner_project}.json
```

Example:

```text
GET https://api.growthepie.com/v1/apps/details/uniswap.json
```

## Key Facts

* Auth: not required
* Rate limit guidance: do not exceed 10 calls per minute
* Path parameter: `owner_project`
* Public discovery source for valid `owner_project`: `labels/projects_filtered.json`

## Key Response Sections

* `last_updated_utc`
* `metrics`
* `kpi_cards`
* `first_seen`
* `chains_by_size`
* `contracts_table`

## Example Response Excerpt

```json
{
  "last_updated_utc": "2026-03-27 05:40:34",
  "first_seen": {
    "polygon_pos": "2020-10-01",
    "ethereum": "2021-01-01",
    "optimism": "2021-11-11",
    "arbitrum": "2022-04-18",
    "base": "2023-07-29"
  },
  "metrics": {
    "txcount": {
      "metric_name": "Transaction Count",
      "avg": true,
      "over_time": {
        "arbitrum": {
          "daily": {
            "types": ["unix", "value"]
          }
        }
      }
    }
  },
  "contracts_table": {
    "7d": {
      "types": []
    }
  }
}
```

## When To Use apps/details/{owner_project}.json

* You need app-level metrics for one project
* You want chain-by-chain activity for one app
* You need first-seen dates or contract-level tables for one project
* You have already confirmed that the `owner_project` exists in `labels/projects_filtered.json`

## When Not To Use apps/details/{owner_project}.json

* You need the full list of valid projects before choosing one project
* You need flat chain-level exports instead of a project detail object

## Caveats

* This endpoint exists for `owner_project` values with mapped contract activity.
* The app detail endpoint is only available for `owner_project` values in `labels/projects_filtered.json`, not for every project in `labels/projects.json`.
* The metric set can vary by project. The `uniswap` example currently exposes metrics such as `txcount`, `daa`, `gas_fees`, `success_rate`, `market_cap`, `token_price`, and `token_volume`.
* Use `labels/projects_filtered.json` before generating code that assumes an app-detail endpoint exists.

## Related Pages

* [What Is owner_project?](../core-concepts/what-is-owner-project.md)
* [Endpoint: labels/projects.json](labels-projects-json.md)
* [Endpoint: labels/projects_filtered.json](labels-projects-filtered-json.md)
