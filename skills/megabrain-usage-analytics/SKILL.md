---
name: megabrain-usage-analytics
description: Pull and analyze request/spend data from MegaBrain to answer questions like which team, model, or endpoint drives usage. Use for reporting or capacity planning.
metadata:
  category: analytics
  product: megabrain
---

# MegaBrain Usage Analytics

## When to Use This Skill

- A user asks "what's driving our AI spend/usage this month"
- Preparing a usage report for finance or leadership
- Investigating a sudden spike in requests or cost

## Steps

1. Pull usage records for the requested time window, broken down by model, project/team, and endpoint.
2. Aggregate by the dimension the question is about (model, team, day) and compute deltas vs. the prior period.
3. Flag anomalies: a single caller or model responsible for a disproportionate share of growth.
4. Cross-reference spikes with deploys or feature launches around the same date.
5. Summarize findings as a short table plus 2-3 sentences of interpretation, not a raw data dump.

## Notes

- Always state the time window and currency/unit basis explicitly in the summary.
- Distinguish "usage grew because adoption grew" (fine) from "usage grew because of inefficient calls" (actionable).
