---
description: Find top apps on a chain with growthepie chain overview data and the live platform.
---

# How To Find Top Apps On A Chain

Use growthepie chain pages and chain overview JSON when you want to see which apps are active on a chain. The live platform is the quickest way to inspect the result, and the chain overview endpoint gives you a structured ecosystem payload you can use in code.

## Explore It Live

* Arbitrum: [https://www.growthepie.com/chains/arbitrum](https://www.growthepie.com/chains/arbitrum)
* Base: [https://www.growthepie.com/chains/base](https://www.growthepie.com/chains/base)

## API Path

* `https://api.growthepie.com/v1/chains/arbitrum/overview.json`

## Example Request

```bash
curl -s https://api.growthepie.com/v1/chains/arbitrum/overview.json
```

## What To Look For

* `data.ecosystem.active_apps`
* `data.ecosystem.apps`

## Caveats

* This endpoint summarizes ecosystem context. It is not a full app directory export.
* Use `labels/projects.json` or `labels/projects_filtered.json` when you need broader project discovery.

## Related Pages

* [Projects And owner_project](../entity-coverage-reference/projects-and-owner-project.md)
* [Endpoint: chains/{origin_key}/overview.json](../api-reference/chain-overview-json.md)
