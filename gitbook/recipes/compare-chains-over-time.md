---
description: Compare multiple chains over time with growthepie exports.
---

# Compare Chains Over Time

This recipe compares transaction count across several chains using the public `txcount` export. Use this recipe when you want a normalized notebook workflow for multi-chain comparisons.

## Example

```python
import pandas as pd
import requests

url = "https://api.growthepie.com/v1/export/txcount.json"
rows = requests.get(url, timeout=30).json()

df = pd.DataFrame(rows)
df["date"] = pd.to_datetime(df["date"])

chains = ["arbitrum", "base", "optimism"]
subset = df[df["origin_key"].isin(chains)]

pivot = subset.pivot_table(
    index="date",
    columns="origin_key",
    values="value",
    aggfunc="sum"
).sort_index()

print(pivot.tail())
```

## Related Pages

* [txcount](../metric-reference/txcount.md)
* [Plot A Timeseries](plot-a-timeseries.md)
