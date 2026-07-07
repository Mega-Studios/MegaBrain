---
name: model-benchmarking
description: Systematically benchmark candidate models on latency, cost, and quality for a specific task using MegaBrain's unified API. Use before adopting a new model or re-validating an existing choice.
metadata:
  category: evaluation
  product: megabrain
---

# Model Benchmarking

## When to Use This Skill

- A new model is released and a user wants to know if it beats the current default
- Building a recurring benchmark to catch quality regressions when providers update models silently

## Steps

1. Define the task's evaluation set (fixed inputs + expected properties or reference answers) — reuse the set from `prompt-ab-testing` if one already exists.
2. Run each candidate model through MegaBrain, recording p50/p95 latency, cost per request, and a quality score.
3. Run the full benchmark at least twice per model to catch latency variance, not a single sample.
4. Store results with the model version/date, since providers update models under the same name over time.
5. Re-run the benchmark on a schedule (e.g. monthly) and diff against the stored baseline to catch silent regressions.

## Notes

- Treat latency and cost as hard constraints, and quality as the thing being optimized within them — not the other way around.
- Report a confidence interval or range, not a single point estimate, when sample sizes are small.
