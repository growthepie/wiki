---
description: Common metric interpretation caveats for growthepie data.
---

# Metric Interpretation Caveats

Metrics answer specific questions and can be misread if used outside their intended scope. This page collects the most important interpretation caveats in one place.

## Common Caveats

* `daa` is an address-level signal, not a person-level user count.
* `txcount` is an activity count, not a throughput or complexity measure.
* `txcosts` is a median transaction cost metric, not total fees paid.
* `fees` is distinct from `app_revenue`.
* `market_cap` and `fdv` are market metrics and can move with token price rather than onchain usage.
* Value metrics such as `tvl` and `stables_mcap` should not be treated as direct activity metrics.

## Related Pages

* [daa](../metric-reference/daa.md)
* [txcount](../metric-reference/txcount.md)
* [txcosts](../metric-reference/txcosts.md)
