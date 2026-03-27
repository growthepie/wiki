---
description: Plot a growthepie time series with pandas and matplotlib.
---

# Plot A Timeseries

This recipe plots a time series for `txcount` on `arbitrum`. Use this recipe when you want a notebook-ready chart from the public exports.

## Example

```python
import matplotlib.pyplot as plt
import pandas as pd
import requests

url = "https://api.growthepie.com/v1/export/txcount.json"
rows = requests.get(url, timeout=30).json()

df = pd.DataFrame(rows)
df["date"] = pd.to_datetime(df["date"])

series = df[df["origin_key"] == "arbitrum"].sort_values("date")

series.plot(x="date", y="value", figsize=(12, 4), title="Arbitrum Transaction Count")
plt.ylabel("txcount")
plt.tight_layout()
plt.show()
```

## Related Pages

* [Load Into pandas](load-into-pandas.md)
* [txcount](../metric-reference/txcount.md)
