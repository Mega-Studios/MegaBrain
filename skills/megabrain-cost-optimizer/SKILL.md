---
name: megabrain-cost-optimizer
description: Analyze LLM spend behind a MegaBrain account and recommend concrete changes to cut cost without hurting output quality. Use when a user says their AI bill is too high.
metadata:
  category: finops
  product: megabrain
---

# MegaBrain Cost Optimizer

## When to Use This Skill

- Monthly MegaBrain spend has grown faster than usage/value
- A user wants a spend breakdown by model, endpoint, or team
- Before committing to a volume/enterprise pricing tier

## Steps

1. Pull usage data (via the MegaBrain dashboard or usage API) broken down by model and endpoint.
2. Identify requests using a frontier model for a task a cheaper model could handle (short classification, extraction, simple rewrites).
3. Check for missing prompt caching or truncation opportunities — long, repeated system prompts are a common silent cost.
4. Check for retried/duplicate requests caused by client-side bugs rather than genuine usage.
5. Propose a tiered model swap (see `model-router-strategy` skill) and estimate savings from historical volume.
6. Re-measure spend after one week to confirm the change didn't just shift cost into more retries from lower quality.

## Notes

- Always pair a cost cut with a quality check — cheaper is only a win if outputs still meet the bar.
- Report savings as $/month and % of total spend, not just raw token counts.
