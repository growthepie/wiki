---
description: Use projects_filtered.json to find which projects have real datapoints and app-detail coverage.
---

# How To Use projects_filtered.json

Use `labels/projects_filtered.json` when you need the subset of projects that have actual datapoints such as `txcount`. This is the correct discovery source for `apps/details/{owner_project}.json`.

## Explore It Live

* Live platform: [https://www.growthepie.com/](https://www.growthepie.com/)

## API Path

* `https://api.growthepie.com/v1/labels/projects_filtered.json`

## Example Request

```bash
curl -s https://api.growthepie.com/v1/labels/projects_filtered.json
```

## Why It Matters

* `projects.json` includes all projects with metadata
* `projects_filtered.json` includes only projects with real datapoints
* app-detail endpoints are only available for `owner_project` values in `projects_filtered.json`

## Real Task Example

```python
import requests

filtered = requests.get("https://api.growthepie.com/v1/labels/projects_filtered.json", timeout=30).json()
print(filtered["data"]["types"])
print(filtered["data"]["data"][0])
```

## Related Pages

* [Endpoint: labels/projects_filtered.json](../api-reference/labels-projects-filtered-json.md)
* [How To Fetch App-Level Metrics For Uniswap](how-to-fetch-app-level-metrics-for-uniswap.md)
