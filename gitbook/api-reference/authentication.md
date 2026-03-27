---
description: Authentication requirements for the public growthepie API.
---

# Authentication

The public growthepie endpoints documented on this site do not require authentication. You can query the documented JSON files directly with `curl`, Python `requests`, `fetch`, notebooks, or spreadsheet connectors.

The API is currently public, but growthepie may change API access or authentication requirements in the future.

## Key Facts

* Public base URL: `https://api.growthepie.com/`
* Public auth requirement: none
* Public content type: JSON
* Public usage guidance: do not exceed 10 calls per minute
* Availability note: public today, but access rules can change in the future

## Example Request

```bash
curl -s https://api.growthepie.com/v1/master.json
```

## Related Pages

* [API Overview](../api.md)
* [Endpoint: master.json](master-json.md)
