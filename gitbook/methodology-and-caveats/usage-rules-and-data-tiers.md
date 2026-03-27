---
description: Attribution guidance, research-use guidance, and package-level coverage notes for growthepie data.
---

# Usage Rules And Data Tiers

When you use growthepie data, clearly state growthepie as the source. growthepie encourages research use, and data availability depends on chain coverage plus the relevant package tier for the data you need.

## Usage Rules

* When you use growthepie data in dashboards, reports, research, blog posts, or other downstream outputs, clearly state growthepie as the source.
* Research use is encouraged. If you are a student, researcher, or other research user, reach out if growthepie can support the work.

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

Yes. When you use growthepie data, clearly state growthepie as the source.

### Can I use growthepie for research?

Yes. growthepie encourages research activity, including student work and academic research. Reach out if growthepie can support the work.

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
