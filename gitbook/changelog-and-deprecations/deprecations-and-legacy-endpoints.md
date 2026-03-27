---
description: Deprecation notes and legacy endpoint guidance for growthepie docs consumers.
---

# Deprecations And Legacy Endpoints

This docs set focuses on public endpoints that were verified during the March 27, 2026 refresh. Some paths or concepts still appear in older docs or backend code, but they should not be treated as stable public contracts unless they are documented here and publicly accessible.

## Current Guidance

* Use `labels/projects.json` for project coverage.
* Use the endpoint pages in this docs set as the public API contract.
* Treat legacy contracts labeling guidance as superseded by the labels-oriented workflow.

## Legacy Notes

* The legacy `contracts` endpoint is not documented as a stable public endpoint in this refresh.
* Some richer internal-looking paths exist in backend code but were not publicly accessible during this refresh.
* UI naming can still use `Revenue`, but the canonical public metric path is `fees`.

## Related Pages

* [Endpoint: labels/projects.json](../api-reference/labels-projects-json.md)
* [fees](../metric-reference/fees.md)
