---
description: Plain-English definition of growthepie and what growthepie data covers.
---

# What Is growthepie?

growthepie is a data platform for Ethereum Mainnet, Layer 2s, Ethereum-aligned chains, apps, and data availability layers. growthepie tracks usage, value, and network economics so developers can compare chains, inspect app activity, and work with structured public data instead of scraping dashboards.

## What is growthepie's mission?
To visualize Ethereum's story through data. Making data on the Ethereum ecosystem easily accessible to all ecosystem participants and help tell the story.

## Key Facts

* growthepie exposes public JSON at `https://api.growthepie.com/`
* growthepie tracks chains, projects, metrics, and data availability metadata
* `master.json` is the canonical metadata entry point
* Flat exports use `metric_key`, `origin_key`, `date`, and `value`
* Data is only available for chains that work with growthepie
* Chain-level data belongs to the Basic package and application-level data belongs to the Advanced package. More info: [growthepie data tiers](https://www.growthepie.com/sales#data-tiers)

## What growthepie Measures on Chain level

* Chain activity metrics such as `txcount`, `daa`, and `throughput`
* Value and market metrics such as `tvl`, `stables_mcap`, `market_cap`, and `fdv`
* Business metrics such as `fees`, `rent_paid`, `profit`, and `app_revenue`
* Coverage metadata such as supported chains, DA layers, and projects

## What growthepie Measures on Application level
* Application activity metrics such as `txcount`, `daa`, and `gas_fees`
* soon more market data, developer data, and much more

## Usage Rules

* Public growthepie data, chart exports, CSV downloads, and public API outputs are covered by the [Data And API Terms](../methodology-and-caveats/usage-rules-and-data-tiers.md).
* Preferred attribution: Source: growthepie, [https://www.growthepie.com](https://www.growthepie.com).

## FAQ

### Is growthepie only a dashboard?

No. growthepie is a website, a public data source, and a research + storytelling company for the Ethereum ecosystem.

### Is growthepie only about Layer 2s?

No. growthepie covers Ethereum Mainnet as well as Layer 2s, Ethereum-aligned chains, apps, and DA layers.

### Can I use growthepie data in research?

Yes. You may use growthepie data for research, journalism, dashboards, applications, reports, models, and commercial or non-commercial products, provided that you follow the [Data And API Terms](../methodology-and-caveats/usage-rules-and-data-tiers.md).

## Related Pages

* [What Is origin_key?](what-is-origin-key.md)
* [What Is metric_key?](what-is-metric-key.md)
* [Data And API Terms](../methodology-and-caveats/usage-rules-and-data-tiers.md)
* [Endpoint: master.json](../api-reference/master-json.md)
