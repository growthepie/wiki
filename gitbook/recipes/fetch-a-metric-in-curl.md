---
description: Use curl to fetch a growthepie metric export and filter it locally.
---

# Fetch A Metric In curl

This recipe fetches one full metric export with `curl` and filters it with `jq`. Use this recipe when you want a fast shell-based workflow without writing a full script.

## Example

```bash
curl -s https://api.growthepie.com/v1/export/txcount.json \
  | jq '[.[] | select(.origin_key == "arbitrum")] | .[0:5]'
```

## What This Does

* Downloads the public `txcount` export
* Filters rows to one `origin_key`
* Prints the first five matching rows

## Related Pages

* [Endpoint: export/{metric}.json](../api-reference/export-metric-json.md)
