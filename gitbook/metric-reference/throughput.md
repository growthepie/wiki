---
description: Definition and usage guidance for the growthepie throughput metric.
---

# throughput

`throughput` measures throughput using the raw series `gas_per_second`. Use `throughput` when you want a chain capacity or throughput view rather than a transaction-count view.

## Key Facts

* Canonical `metric_id`: `throughput`
* Canonical `metric_key`: `gas_per_second`
* Unit: `Mgas/s`
* Hourly detail available: yes
* Coverage: see `master.json.metrics.throughput.supported_chains`
* Common search synonyms: gas per second, throughput

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/throughput.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "gas_per_second",
    "origin_key": "arbitrum",
    "date": "2026-03-01",
    "value": 5.72
  }
]
```

## When To Use throughput

* Compare processing throughput across chains
* Track throughput changes over time

## When Not To Use throughput

* You need transaction count instead of gas throughput
* You need fee cost or value metrics

## Caveats

* `throughput` is not the same thing as `txcount`.
* The unit is `Mgas/s`, not raw transaction count.

## Related Pages

* [txcount](txcount.md)
* [txcosts](txcosts.md)
