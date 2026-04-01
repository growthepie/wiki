---
description: Definition and usage guidance for the growthepie txcosts metric.
---

# txcosts

`txcosts` measures transaction costs using median fee series. Use `txcosts` when you want a cost-per-transaction style metric rather than total fees paid.

## Key Facts

* Canonical `metric_id`: `txcosts`
* Canonical `metric_key` values: `txcosts_median_usd`, `txcosts_median_eth`
* Unit: USD and ETH
* Hourly detail available: yes
* Coverage: see `master.json.metrics.txcosts.supported_chains`
* Common search synonyms: median fee, transaction cost

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/txcosts.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "txcosts_median_usd",
    "origin_key": "base",
    "date": "2026-03-01",
    "value": 0.0041
  },
  {
    "metric_key": "txcosts_median_eth",
    "origin_key": "base",
    "date": "2026-03-01",
    "value": 0.0000013
  }
]
```

## When To Use txcosts

* Compare typical transaction cost across chains
* Track fee affordability trends over time

## When Not To Use txcosts

* You need total fees paid instead of typical per-transaction cost
* You need transaction volume

## Caveats

* `txcosts` is a median-style cost metric, not total cost.
* Aggregate comparisons across chains use a weighted-mean style aggregation in growthepie metadata.

## Related Pages

* [fees](fees.md)
* [throughput](throughput.md)
* [Endpoint: fees/table.json](../api-reference/fees-table-json.md)
