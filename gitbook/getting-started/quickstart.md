---
description: Copy-pasteable quickstart examples for the growthepie API in curl, Python, and JavaScript.
---

# Quickstart

This page answers the most common first question directly: how do I make a correct growthepie API request right now? The examples below are complete, runnable, and use real public endpoints that do not require authentication.

## Key Facts

* Base URL: `https://api.growthepie.com/`
* Auth: No authentication required for the public endpoints documented here
* Best first endpoint: `https://api.growthepie.com/v1/master.json`
* Flat export shape: `metric_key`, `origin_key`, `date`, `value`

## curl

```bash
curl -s https://api.growthepie.com/v1/export/txcount.json
```

## Python

```python
import requests

url = "https://api.growthepie.com/v1/export/txcount.json"
response = requests.get(url, timeout=30)
response.raise_for_status()

rows = response.json()
print(f"rows={len(rows)}")
print(rows[0])
```

## JavaScript / TypeScript

```ts
const url = "https://api.growthepie.com/v1/export/txcount.json";

const response = await fetch(url);
if (!response.ok) {
  throw new Error(`Request failed with status ${response.status}`);
}

const rows = await response.json();
console.log(`rows=${rows.length}`);
console.log(rows[0]);
```

## Example Response

```json
[
  {
    "metric_key": "txcount",
    "origin_key": "arbitrum",
    "date": "2021-05-29",
    "value": 9.0
  }
]
```

## Real Task: Fetch One Chain's Transaction Count History

```python
import requests

url = "https://api.growthepie.com/v1/export/txcount.json"
rows = requests.get(url, timeout=30).json()

arbitrum_rows = [row for row in rows if row["origin_key"] == "arbitrum"]
print(arbitrum_rows[:3])
```

## FAQ

### What should I fetch before choosing an `origin_key`?

Fetch `master.json`. `master.json` is the canonical metadata file for supported chains and supported metrics.

### When should I use `fundamentals.json` instead?

Use `fundamentals.json` when you want many fundamental metrics together in one 90-day daily export.

## Related Pages

* [Choose The Right Endpoint](choose-the-right-endpoint.md)
* [Endpoint: export/{metric}.json](../api-reference/export-metric-json.md)
* [Fetch A Metric In curl](../recipes/fetch-a-metric-in-curl.md)
