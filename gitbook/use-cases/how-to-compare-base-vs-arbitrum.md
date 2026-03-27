---
description: Compare Base and Arbitrum with growthepie using live dashboards and the API.
---

# How To Compare Base vs Arbitrum

Use growthepie to compare Base and Arbitrum when you want a grounded view of activity, costs, value, and app usage. Start on the live chain pages, then use `master.json` and the metric exports to reproduce the comparison programmatically.

## Explore It Live

* Base: [https://www.growthepie.com/chains/base](https://www.growthepie.com/chains/base)
* Arbitrum: [https://www.growthepie.com/chains/arbitrum](https://www.growthepie.com/chains/arbitrum)

## API Paths

* Discovery: `https://api.growthepie.com/v1/master.json`
* Chain overview: `https://api.growthepie.com/v1/chains/base/overview.json`
* Chain overview: `https://api.growthepie.com/v1/chains/arbitrum/overview.json`

## Example Request

```bash
curl -s https://api.growthepie.com/v1/chains/base/overview.json
```

## What To Compare

* `txcount` for raw activity
* `daa` for address-level activity
* `txcosts` for median transaction costs
* `stables_mcap` or `tvl` for value

## Caveats

* Different metrics answer different questions. Do not compare `txcount` and `tvl` as if they measured the same thing.
* Exclude any chain whose `deployment` or `deployment_flag` is `DEV` or `ARCHIVED`.

## Related Pages

* [How To Find Which Metrics A Chain Supports](how-to-find-which-metrics-a-chain-supports.md)
* [How To Get Chain Overview Data For Arbitrum](how-to-get-chain-overview-data-for-arbitrum.md)
