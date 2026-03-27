---
description: Reference for the growthepie labels/projects.json endpoint.
---

# Endpoint: labels/projects.json

`labels/projects.json` is the public project coverage endpoint. `labels/projects.json` returns project metadata as a typed table, which makes it useful when you want to map `owner_project` identifiers to human-readable names, descriptions, websites, categories, and other project attributes.

## Request

```text
GET https://api.growthepie.com/v1/labels/projects.json
```

## Key Facts

* Auth: not required
* Response type: object with `last_updated_utc` and a typed table
* Table columns are listed in `data.types`
* Table rows are listed in `data.data`

## Example Response

```json
{
  "last_updated_utc": "2026-03-27 05:35:04",
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
      "sub_category",
      "main_category",
      "sub_categories"
    ],
    "data": [
      [
        "adsbaazar",
        "Adsbaazar",
        "Adsbaazar is an India-based vehicle branding and outdoor advertising service provider.",
        null,
        null,
        "https://www.adsbaazar.com/",
        null,
        null,
        "Stablecoin",
        "Token Transfers",
        ["stablecoin"]
      ]
    ]
  }
}
```

## When To Use labels/projects.json

* You need the canonical `owner_project` list
* You need a project display name or description
* You need app or project coverage metadata
* You need to discover valid `owner_project` values before calling `apps/details/{owner_project}.json`

## Caveats

* `labels/projects.json` is a table-oriented payload, not a flat list of objects.
* Consumers should map `data.types` to each row in `data.data` before building objects locally.

## Related Pages

* [Projects And owner_project](../entity-coverage-reference/projects-and-owner-project.md)
* [Endpoint: apps/details/{owner_project}.json](app-detail-json.md)
