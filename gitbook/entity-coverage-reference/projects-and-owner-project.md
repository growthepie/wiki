---
description: Reference for growthepie project coverage and owner_project identifiers.
---

# Projects And owner_project

`owner_project` is the canonical project identifier exposed by `labels/projects.json`. Use `owner_project` when you need to map project metadata, join project coverage with downstream analysis workflows, or fetch a project detail response from `apps/details/{owner_project}.json`.

## Key Facts

* Canonical source: `https://api.growthepie.com/v1/labels/projects.json`
* Last verified in this docs refresh: March 27, 2026
* Live project count at that time: 6,650
* Core fields: `owner_project`, `display_name`, `description`, `website`, `main_category`, `sub_category`

## Example Request

```bash
curl -s https://api.growthepie.com/v1/labels/projects.json
```

## Example Use

Use `labels/projects.json` when you need to answer questions such as:

* Which `owner_project` values are covered?
* What human-readable name matches a given `owner_project`?
* Which categories and subcategories are assigned to a project?
* Which project detail JSON path should I call for a given app?

## Caveats

* The payload is a typed table, not a list of JSON objects.
* Coverage size changes over time, so prefer the live endpoint over hardcoded lists.

## Related Pages

* [What Is owner_project?](../core-concepts/what-is-owner-project.md)
* [Endpoint: labels/projects.json](../api-reference/labels-projects-json.md)
* [Endpoint: apps/details/{owner_project}.json](../api-reference/app-detail-json.md)
* [Chain vs App vs Ecosystem Metrics](../core-concepts/chain-vs-app-vs-ecosystem-metrics.md)
