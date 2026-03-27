---
description: Learn what origin_key means in growthepie and where to find valid origin_key values.
---

# What Is origin_key?

`origin_key` is the canonical growthepie identifier for a covered entity, most commonly a chain. You use `origin_key` values such as `arbitrum`, `base`, `ethereum`, or `zksync_era` to filter flat exports and to address richer endpoints such as `chains/{origin_key}/overview.json`.

## Key Facts

* `origin_key` is lowercase and stable enough to be used in code and URLs
* The canonical list of public chain `origin_key` values lives in `master.json`
* `origin_key` appears in flat export rows together with `metric_key`, `date`, and `value`
* `origin_key` is not a display name; for example, `arbitrum` maps to the display name `Arbitrum One`

## Example

```json
{
  "metric_key": "txcount",
  "origin_key": "arbitrum",
  "date": "2021-05-29",
  "value": 9.0
}
```

## Synonyms And Nearby Terms

* Search synonym: chain key
* Search synonym: chain slug
* Not the same thing: display name
* Not the same thing: `owner_project`

## FAQ

### Where do I get valid `origin_key` values?

Use `master.json`. Each chain entry in `master.json.chains` includes metadata and supported metrics.

### Does `origin_key` only refer to chains?

In the public endpoints documented on this site, `origin_key` is primarily used for chains. Project coverage uses `owner_project` instead.

## Related Pages

* [Supported Chains And origin_key](../entity-coverage-reference/supported-chains-and-origin-key.md)
* [Endpoint: master.json](../api-reference/master-json.md)
