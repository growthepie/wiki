---
description: Benchmark questions and a manual checklist for validating AI-friendly growthepie docs.
---

# AI Validation Checklist

Use these questions to test whether the docs are easy for both humans and AI systems to retrieve, quote, and use correctly.

## Benchmark Questions

1. What is growthepie?
2. What is `origin_key`?
3. What is `owner_project`?
4. What is `metric_key`?
5. What is the difference between `metric_id` and `metric_key`?
6. Which endpoint should I call first to discover supported chains?
7. What does `master.json` return?
8. What does `fundamentals.json` return?
9. Is `fundamentals.json` full history?
10. How do I fetch `txcount` for one chain?
11. How do I fetch the full `txcount` export across chains?
12. How do I compare multiple chains over time?
13. How do I load growthepie data into pandas?
14. How do I fetch growthepie data in JavaScript?
15. What does `daa` mean?
16. What does `txcosts` mean?
17. What is the difference between `fees` and `app_revenue`?
18. What units does `throughput` use?
19. Which chains support `tvl`?
20. Which data availability layers are covered?
21. Which endpoint exposes project coverage?
22. What is the difference between `projects.json` and `projects_filtered.json`?
23. Which endpoint exposes app detail for one `owner_project`?
24. Which `owner_project` values can be used with `apps/details/{owner_project}.json`?
25. What rate limit should AI agents follow?
26. Which chains should be excluded because `deployment` or `deployment_flag` is `DEV` or `ARCHIVED`?
27. Which endpoints expose `last_updated_utc`?
28. Which metrics have hourly detail?
29. Are any public endpoints deprecated or legacy?

## Manual Validation Checklist

* The page answers its main question directly in the first paragraph.
* The page defines the canonical terms explicitly.
* The page includes at least one runnable example when the topic is procedural.
* The page includes caveats when the topic can be misinterpreted.
* The page is linked from `SUMMARY.md`.
* The page is text-first and does not depend on screenshots to explain the concept.
* The page uses consistent names such as `origin_key`, `metric_key`, `value`, and `date`.
* The page points to a source-of-truth artifact or endpoint when appropriate.
