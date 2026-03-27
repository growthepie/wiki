---
description: Find which metrics a chain supports in growthepie before generating queries or code.
---

# How To Find Which Metrics A Chain Supports

Use `master.json` to discover which metrics a chain supports before you query exports or generate code. This avoids invalid assumptions and lets you exclude unsupported combinations up front.

## Explore It Live

* Live platform: [https://www.growthepie.com/](https://www.growthepie.com/)

## API Path

* `https://api.growthepie.com/v1/master.json`

## Example Request

```bash
curl -s https://api.growthepie.com/v1/master.json
```

## Real Task Example

```python
import requests

master = requests.get("https://api.growthepie.com/v1/master.json", timeout=30).json()
print(master["chains"]["arbitrum"]["supported_metrics"])
```

## Caveats

* Check `deployment` or `deployment_flag` as well as `supported_metrics`.
* Use the live metadata instead of hardcoding support tables.

## Related Pages

* [Endpoint: master.json](../api-reference/master-json.md)
* [How To Identify Chains With Stale Data](how-to-identify-chains-with-stale-data.md)
