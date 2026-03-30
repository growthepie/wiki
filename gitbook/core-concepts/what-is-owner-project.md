---
description: Learn what owner_project means in growthepie and where to find valid owner_project values.
---

# What Is owner_project?

`owner_project` is the canonical growthepie identifier for a covered app or project. You use `owner_project` values such as `uniswap` to map project metadata from `labels/projects.json` and to fetch project detail JSON from `apps/details/{owner_project}.json`.

In practice, `owner_project` is the application-level key. growthepie application metrics are mostly based on smart contracts mapped to that `owner_project`.

## Key Facts

* `owner_project` is the canonical project key for app-level coverage
* The canonical list of public `owner_project` values lives in `labels/projects.json`
* `owner_project` is not the same thing as a display name
* `owner_project` is not the same thing as `origin_key`
* App-level metrics are mostly based on mapped smart contracts

## Example

```json
[
  "uniswap",
  "Uniswap",
  "Uniswap is a decentralized exchange protocol."
]
```

## Synonyms And Nearby Terms

* Search synonym: project key
* Search synonym: app slug
* Not the same thing: display name
* Not the same thing: `origin_key`

## FAQ

### Where do I get valid `owner_project` values?

Use `labels/projects.json` for the full metadata universe. Use `labels/projects_filtered.json` when you need the subset of `owner_project` values that have actual datapoints and can be used with app-detail endpoints.

### What do I use `owner_project` for after discovery?

Use `owner_project` in app-level detail paths such as `apps/details/{owner_project}.json`.

## Related Pages

* [Projects And owner_project](../entity-coverage-reference/projects-and-owner-project.md)
* [Endpoint: labels/projects.json](../api-reference/labels-projects-json.md)
* [Endpoint: labels/projects_filtered.json](../api-reference/labels-projects-filtered-json.md)
* [Endpoint: apps/details/{owner_project}.json](../api-reference/app-detail-json.md)
