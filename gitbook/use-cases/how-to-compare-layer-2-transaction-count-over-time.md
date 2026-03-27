---
description: Compare Layer 2 transaction count over time with growthepie and the public API.
---

# How To Compare Layer 2 Transaction Count Over Time

Use growthepie when you want to compare transaction activity across Layer 2s over time. The fastest path is to explore the live chart on growthepie.com and then use `export/txcount.json` or `metrics/chains/{origin_key}/txcount.json` when you need the underlying data in code.

## Explore It Live

* Live platform: [https://www.growthepie.com/fundamentals/transaction-count](https://www.growthepie.com/fundamentals/transaction-count)

## API Paths

* Broad export: `https://api.growthepie.com/v1/export/txcount.json`
* Rich per-chain detail: `https://api.growthepie.com/v1/metrics/chains/arbitrum/txcount.json`

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/txcount.json
```

## Real Task Example

```python
import pandas as pd
import requests

rows = requests.get("https://api.growthepie.com/v1/export/txcount.json", timeout=30).json()
df = pd.DataFrame(rows)
df["date"] = pd.to_datetime(df["date"])

chains = ["arbitrum", "base", "optimism"]
comparison = df[df["origin_key"].isin(chains)].pivot_table(
    index="date",
    columns="origin_key",
    values="value",
    aggfunc="sum",
).sort_index()

print(comparison.tail())
```

## Caveats

* `txcount` is activity count, not user count.
* Do not exceed 10 API calls per minute.

## Related Pages

* [txcount](../metric-reference/txcount.md)
* [How To Compare Base vs Arbitrum](how-to-compare-base-vs-arbitrum.md)
