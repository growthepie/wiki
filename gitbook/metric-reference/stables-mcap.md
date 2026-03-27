---
description: Definition and usage guidance for the growthepie stables_mcap metric.
---

# stables_mcap

`stables_mcap` measures stablecoin supply on a covered chain. Use `stables_mcap` when you want a stablecoin-focused value metric rather than a broader secured-value metric such as `tvl`.

## Key Facts

* Canonical `metric_id`: `stables_mcap`
* Canonical `metric_key` values: `stables_mcap`, `stables_mcap_eth`
* Unit: USD and ETH
* Hourly detail available: no
* Coverage: see `master.json.metrics.stables_mcap.supported_chains`
* Common search synonyms: stablecoin market cap, stablecoin supply

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/stables_mcap.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "stables_mcap",
    "origin_key": "base",
    "date": "2026-03-01",
    "value": 3400000000.0
  },
  {
    "metric_key": "stables_mcap_eth",
    "origin_key": "base",
    "date": "2026-03-01",
    "value": 1140000.0
  }
]
```

## When To Use stables_mcap

* Track stablecoin presence on a chain
* Compare stablecoin-denominated value across chains

## When Not To Use stables_mcap

* You need overall secured value
* You need transaction activity or fee metrics

## Caveats

* `stables_mcap` is narrower than `tvl`.
* Currency-paired raw series can appear in both USD and ETH form.

## Related Pages

* [tvl](tvl.md)
* [fees](fees.md)
