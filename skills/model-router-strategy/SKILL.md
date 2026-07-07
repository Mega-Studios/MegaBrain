---
name: model-router-strategy
description: Design a routing strategy across MegaBrain's 500+ models to balance cost, latency, and quality for a given workload. Use when picking or re-evaluating which model(s) an app should call.
metadata:
  category: infrastructure
  product: megabrain
---

# Model Router Strategy

Help the user choose which model(s) MegaBrain should route a workload to, instead of hardcoding a single provider.

## When to Use This Skill

- Standing up a new feature that calls an LLM and no model has been chosen yet
- Diagnosing why current model choice is too slow, too expensive, or too weak
- Splitting traffic across multiple models (e.g. cheap model for simple requests, frontier model for hard ones)

## Steps

1. **Classify the workload**: latency-sensitive (chat, autocomplete) vs. batch/offline (summarization, extraction).
2. **Set a quality floor**: what's the minimum acceptable output quality? Prefer the cheapest model at or above that floor.
3. **Check MegaBrain's model catalog** (`getmegabrain.com/models`) for candidates matching the required context window, tool-use support, and modality.
4. **Propose a tiered route**: a fast/cheap default model plus an escalation path to a stronger model on failure or low-confidence output.
5. **Wire it through MegaBrain's single OpenAI-compatible endpoint** — only the `model` field changes between tiers, so no separate SDKs or base URLs are needed per provider.
6. **Recommend measuring** p50/p95 latency, cost per request, and error rate for two weeks before locking in the route.

## Notes

- Don't default to the most capable model everywhere — most production traffic doesn't need it.
- Keep the routing decision in config, not scattered across call sites, so it can be tuned without a redeploy.
