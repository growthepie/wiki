---
description: Benchmark questions and a manual checklist for validating AI-friendly growthepie docs.
---

# AI Validation Checklist

Use these questions to test whether the docs are easy for both humans and AI systems to retrieve, quote, and use correctly.

## Benchmark Questions

1. What is growthepie?
2. What is `origin_key`?
3. What is `metric_key`?
4. What is the difference between `metric_id` and `metric_key`?
5. Which endpoint should I call first to discover supported chains?
6. What does `master.json` return?
7. What does `fundamentals.json` return?
8. Is `fundamentals.json` full history?
9. How do I fetch `txcount` for one chain?
10. How do I fetch the full `txcount` export across chains?
11. How do I compare multiple chains over time?
12. How do I load growthepie data into pandas?
13. How do I fetch growthepie data in JavaScript?
14. What does `daa` mean?
15. What does `txcosts` mean?
16. What is the difference between `fees` and `app_revenue`?
17. What units does `throughput` use?
18. Which chains support `tvl`?
19. Which data availability layers are covered?
20. Which endpoint exposes project coverage?
21. What does `owner_project` mean?
22. Which endpoints expose `last_updated_utc`?
23. Which metrics have hourly detail?
24. Are any public endpoints deprecated or legacy?

## Manual Validation Checklist

* The page answers its main question directly in the first paragraph.
* The page defines the canonical terms explicitly.
* The page includes at least one runnable example when the topic is procedural.
* The page includes caveats when the topic can be misinterpreted.
* The page is linked from `SUMMARY.md`.
* The page is text-first and does not depend on screenshots to explain the concept.
* The page uses consistent names such as `origin_key`, `metric_key`, `value`, and `date`.
* The page points to a source-of-truth artifact or endpoint when appropriate.
