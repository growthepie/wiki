---
description: Export growthepie data to CSV for spreadsheet or notebook workflows.
---

# Export To CSV

This recipe downloads one metric export and writes it to CSV. Use this recipe when you want a local file for spreadsheet workflows, versioned data snapshots, or notebook inputs.

## Example

```python
import csv
import requests

url = "https://api.growthepie.com/v1/export/txcount.json"
rows = requests.get(url, timeout=30).json()

with open("txcount.csv", "w", newline="", encoding="utf-8") as f:
    writer = csv.DictWriter(f, fieldnames=["metric_key", "origin_key", "date", "value"])
    writer.writeheader()
    writer.writerows(rows)

print("Wrote txcount.csv")
```

## Related Pages

* [Fetch growthepie Data In Python](fetch-growthepie-data-in-python.md)
* [Endpoint: export/{metric}.json](../api-reference/export-metric-json.md)
