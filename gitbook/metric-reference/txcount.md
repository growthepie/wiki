---
description: Definition and usage guidance for the growthepie txcount metric.
---

# txcount

`txcount` measures transaction count for a covered chain. Use `txcount` when you want to compare how many transactions a chain processed over time or across chains.

## Key Facts

* Canonical `metric_id`: `txcount`
* Canonical `metric_key`: `txcount`
* Unit: count
* Hourly detail available: yes
* Coverage: see `master.json.metrics.txcount.supported_chains`
* Common search synonyms: transaction count, daily transactions

## Example Request

```bash
curl -s https://api.growthepie.com/v1/export/txcount.json
```

## Example Response Excerpt

```json
[
  {
    "metric_key": "txcount",
    "origin_key": "arbitrum",
    "date": "2021-05-29",
    "value": 9.0
  }
]
```

## When To Use txcount

* Compare chain activity over time
* Rank chains by raw transaction volume
* Build a daily or hourly activity chart

## When Not To Use txcount

* You need a user proxy instead of an activity count
* You need fee or cost information

## Caveats

* `txcount` counts transactions, not unique users.
* `txcount` does not normalize for transaction complexity or gas usage.

## Related Pages

* [daa](daa.md)
* [throughput](throughput.md)
