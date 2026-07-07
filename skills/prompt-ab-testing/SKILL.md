---
name: prompt-ab-testing
description: Run the same prompt across multiple models (Claude, GPT, Gemini, Llama, etc.) through MegaBrain and compare outputs to choose the best model for a task. Use before locking in a model choice.
metadata:
  category: evaluation
  product: megabrain
---

# Prompt A/B Testing Across Models

## When to Use This Skill

- Choosing between models for a new feature
- A user suspects a cheaper model would perform just as well as the current one

## Steps

1. Collect 15-30 representative real inputs (not synthetic toy examples) for the task.
2. Send each input to every candidate model through MegaBrain's single API, varying only the `model` field.
3. Score outputs against a rubric relevant to the task (accuracy, format compliance, tone) — use a stronger model as judge if human review isn't feasible for every sample.
4. Record cost and latency per model alongside quality score.
5. Plot quality vs. cost and pick the model on the efficient frontier, not simply the highest-scoring one.
6. Re-run the comparison periodically — model quality and pricing both change over time.

## Notes

- Keep the prompt and sampling parameters identical across models so the comparison is fair.
- Store the eval set so future model releases can be checked against the same baseline.
