---
description: Reference for the growthepie labels/projects_filtered.json endpoint.
---

# Endpoint: labels/projects_filtered.json

`labels/projects_filtered.json` is the filtered project coverage endpoint. `labels/projects_filtered.json` is a subset of `labels/projects.json` and only includes projects that currently have actual datapoints, such as `txcount`.

## Request

```text
GET https://api.growthepie.com/v1/labels/projects_filtered.json
```

## Key Facts

* Auth: not required
* Response type: object with `last_updated_utc` and a typed table
* Use case: discover which `owner_project` values have actual datapoints
* App-detail dependency: `apps/details/{owner_project}.json` is only available for `owner_project` values in this filtered subset
* Last verified in this docs refresh: March 27, 2026
* Live filtered project count at that time: 757

## Example Response

```json
{
  "last_updated_utc": "2026-03-27 05:40:42",
  "data": {
    "types": [
      "owner_project",
      "display_name",
      "description",
      "main_github",
      "twitter",
      "website",
      "logo_path",
      "token_symbol",
      "txcount",
      "active_on",
      "ecosystem_rank",
      "sub_category",
      "main_category",
      "sub_categories",
      "features"
    ],
    "data": [
      [
        "polymarket",
        "Polymarket",
        "Polymarket is a decentralized blockchain-based prediction market platform.",
        "polymarket",
        "Polymarket",
        "https://polymarket.com/",
        "polymarket.png",
        null,
        125438595.0,
        {
          "polygon_pos": 125438595
        },
        1,
        "Prediction Markets",
        "Finance",
        [
          "erc4337",
          "prediction_markets"
        ],
        [
          "Dummy",
          "Swap",
          "Lending",
          "Bridge",
          "Trading"
        ]
      ]
    ]
  }
}
```

## When To Use labels/projects_filtered.json

* You need the subset of projects that have real datapoints
* You need to discover valid `owner_project` values for `apps/details/{owner_project}.json`
* You need project coverage plus datapoint-aware fields such as `txcount`, `active_on`, or `ecosystem_rank`

## When Not To Use labels/projects_filtered.json

* You need the full metadata universe, including projects that do not currently have datapoints

## Caveats

* `labels/projects_filtered.json` is a subset of `labels/projects.json`.
* This endpoint is the correct discovery source for app-detail endpoints.
* The payload is a typed table, not a list of JSON objects.

## Related Pages

* [Endpoint: labels/projects.json](labels-projects-json.md)
* [Endpoint: apps/details/{owner_project}.json](app-detail-json.md)
* [Projects And owner_project](../entity-coverage-reference/projects-and-owner-project.md)
