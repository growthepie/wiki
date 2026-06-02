---
description: Data and API terms, attribution guidance, fair-use guidance, and package-level coverage notes for growthepie data.
---

# Data And API Terms

Last updated: June 2, 2026.

These Data and API Terms apply to public growthepie data, chart exports, CSV downloads, public API outputs, and other datasets published by growthepie unless a more specific notice says otherwise.

These terms do not replace any separate agreement we may have with you, and they do not grant rights in third-party material, trademarks, logos, brand assets, or data that is clearly governed by another source or license.

## Open Use With Attribution

Unless otherwise stated, growthepie data is copyright or database-right protected material of orbal GmbH / growthepie where protectable, and may be used, shared, and adapted under the Creative Commons Attribution 4.0 International license: [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

You may use the data for research, journalism, dashboards, applications, reports, models, and commercial or non-commercial products, provided that you give appropriate credit and do not imply that growthepie endorses you or your use.

Preferred attribution:

* Source: growthepie, [https://www.growthepie.com](https://www.growthepie.com).
* For chart screenshots or reports, include Source: growthepie near the chart or in the source notes.
* For API-backed products, include a source note in your documentation, data source list, footer, or another reasonable location.
* Where practical, link to the relevant growthepie page, chart, API endpoint, or [https://www.growthepie.com](https://www.growthepie.com).
* If you modify, transform, or combine the data, make that clear where it matters for interpretation.

## Third-Party And Upstream Sources

growthepie combines public blockchain data, own analysis, and selected third-party or upstream data sources. Some metrics, labels, or datasets may include source-specific terms, attribution requirements, or restrictions.

If a chart, API response, documentation page, or source list names another provider, you are responsible for respecting that provider's applicable terms in addition to these terms.

## API Access And Fair Use

Public API access is provided to support open research, builders, ecosystem analysis, and community tools. We may apply rate limits, caching, access controls, or other technical measures to keep the service reliable.

Do not use the API or website in a way that degrades availability, bypasses limits, probes security, overwhelms infrastructure, or misrepresents request origin. For high-volume, commercial, or production-critical use, contact us before relying on the service.

## No Warranty

Data is provided as-is and as-available. It may be incomplete, delayed, inaccurate, changed, reclassified, or removed. We do not guarantee uninterrupted API availability, exact historical continuity, or suitability for a specific purpose.

growthepie is an analytics and educational platform. Nothing on the website, in chart exports, or in API data is financial, investment, legal, tax, or professional advice.

## No Endorsement

Attribution to growthepie does not mean that growthepie sponsors, approves, verifies, or endorses your work, product, analysis, conclusions, or organization.

## Changes

We may update these Data and API Terms when our datasets, API, licensing approach, upstream sources, or legal requirements change. The date at the top shows when these terms were last updated.

Questions about data reuse, attribution, high-volume API use, or commercial partnerships can be sent to [matthias@orbal-analytics.com](mailto:matthias@orbal-analytics.com).

## Coverage And Package Notes

* Data is only available for chains that work with growthepie.
* Chain-level data is part of the Basic package.
* Application-level data is part of the Advanced package.
* Commercial packaging details: [growthepie data tiers](https://www.growthepie.com/sales#data-tiers)
* The API is currently public, but growthepie may change access, packaging, or authentication requirements in the future.

## How To Think About Coverage

* `master.json` is the canonical source for chain and metric coverage.
* `labels/projects.json` is the broad metadata universe for projects.
* `labels/projects_filtered.json` is the subset of `owner_project` values with real datapoints such as `txcount`.
* `apps/details/{owner_project}.json` is only available for `owner_project` values in `labels/projects_filtered.json`.

## FAQ

### Do I need to attribute growthepie?

Yes. Preferred attribution is: Source: growthepie, [https://www.growthepie.com](https://www.growthepie.com).

### Can I use growthepie for research?

Yes. You may use growthepie data for research, journalism, dashboards, applications, reports, models, and commercial or non-commercial products, provided that you follow these terms.

### Is data available for every chain?

No. Data is only available for chains that work with growthepie. Use `master.json` to verify live chain coverage before building against an assumption.

### Which package includes app-level data?

Application-level data is part of the Advanced package. Chain-level data is part of the Basic package. The current package page is [growthepie data tiers](https://www.growthepie.com/sales#data-tiers).

### Will the API always remain public?

Not necessarily. The API is currently public, but growthepie may change access or authentication requirements in the future.

## Related Pages

* [What Is growthepie?](../core-concepts/what-is-growthepie.md)
* [API Overview](../api.md)
* [Endpoint: master.json](../api-reference/master-json.md)
* [Endpoint: labels/projects_filtered.json](../api-reference/labels-projects-filtered-json.md)
* [Endpoint: apps/details/{owner_project}.json](../api-reference/app-detail-json.md)
