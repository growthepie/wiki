---
description: Use Python requests to fetch growthepie data safely.
---

# Fetch growthepie Data In Python

This recipe fetches `fundamentals.json` in Python and prints a few filtered rows. Use this recipe when you want a lightweight script without adding pandas immediately.

## Example

```python
import requests

url = "https://api.growthepie.com/v1/fundamentals.json"
response = requests.get(url, timeout=30)
response.raise_for_status()

rows = response.json()
filtered = [
    row for row in rows
    if row["origin_key"] == "arbitrum" and row["metric_key"] == "txcount"
]

print(filtered[:5])
```

## Related Pages

* [Load Into pandas](load-into-pandas.md)
* [Endpoint: fundamentals.json](../api-reference/fundamentals-json.md)
