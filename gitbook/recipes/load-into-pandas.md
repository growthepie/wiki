---
description: Load growthepie fundamentals data into a pandas DataFrame.
---

# Load Into pandas

This recipe loads `fundamentals.json` into pandas and filters it to one chain and one metric. Use this recipe when you want a notebook-friendly workflow.

## Example

```python
import pandas as pd
import requests

url = "https://api.growthepie.com/v1/fundamentals.json"
response = requests.get(url, timeout=30)
response.raise_for_status()

df = pd.DataFrame(response.json())
df["date"] = pd.to_datetime(df["date"])

subset = df[
    (df["origin_key"] == "arbitrum") &
    (df["metric_key"] == "txcount")
].sort_values("date")

print(subset.tail())
```

## Related Pages

* [Compare Chains Over Time](compare-chains-over-time.md)
* [Plot A Timeseries](plot-a-timeseries.md)
