---
description: Compare stablecoin supply across chains with growthepie and stables_mcap exports.
---

# How To Compare Stablecoin Supply Across Chains

Use growthepie when you want to compare stablecoin supply across Ethereum and Layer 2s. The live platform gives you the fastest visual read, and `export/stables_mcap.json` gives you the underlying rows for notebooks and dashboards.

## Explore It Live

* Live platform: [https://www.growthepie.com/fundamentals/stablecoin-market-cap](https://www.growthepie.com/fundamentals/stablecoin-market-cap)

## API Path

* `https://api.growthepie.com/v1/export/stables_mcap.json`

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/stables_mcap.json
```

## Real Task Example

```python
import pandas as pd
import requests

rows = requests.get("https://api.growthepie.com/v1/export/stables_mcap.json", timeout=30).json()
df = pd.DataFrame(rows)

usd_rows = df[df["metric_key"] == "stables_mcap"]
latest = usd_rows.sort_values("date").groupby("origin_key").tail(1)
print(latest[["origin_key", "date", "value"]].sort_values("value", ascending=False).head(10))
```

## Caveats

* `stables_mcap` is narrower than `tvl`.
* Currency-paired raw series exist in both USD and ETH form.

## Related Pages

* [stables_mcap](../metric-reference/stables-mcap.md)
* [tvl](../metric-reference/tvl.md)
