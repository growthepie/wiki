---
description: Use owner_project correctly in growthepie project coverage and app-detail endpoints.
---

# How To Use owner_project In The growthepie API

Use `owner_project` as the canonical project identifier in growthepie app-level endpoints. Start with `labels/projects.json` for the full metadata universe, then use `labels/projects_filtered.json` to find which `owner_project` values have actual datapoints and app-detail coverage.

## Explore It Live

* Live platform: [https://www.growthepie.com/](https://www.growthepie.com/)

## API Paths

* Full metadata: `https://api.growthepie.com/v1/labels/projects.json`
* Filtered subset: `https://api.growthepie.com/v1/labels/projects_filtered.json`
* App detail: `https://api.growthepie.com/v1/apps/details/uniswap.json`

## Example Request

```bash
curl -s https://api.growthepie.com/v1/labels/projects_filtered.json
```

## Caveats

* `owner_project` is not the same thing as `origin_key`.
* Not every `owner_project` in `projects.json` has an app-detail endpoint.

## Related Pages

* [What Is owner_project?](../core-concepts/what-is-owner-project.md)
* [How To Use projects_filtered.json](how-to-use-projects-filtered-json.md)
