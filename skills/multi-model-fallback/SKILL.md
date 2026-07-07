---
name: multi-model-fallback
description: Implement automatic failover across models/providers behind MegaBrain when a call errors, times out, or is rate-limited. Use when a user needs higher reliability than any single provider offers.
metadata:
  category: reliability
  product: megabrain
---

# Multi-Model Fallback

## When to Use This Skill

- Production traffic occasionally fails due to a single provider's outage or rate limit
- A user wants uptime higher than any one upstream model provider guarantees

## Steps

1. Define a primary model and one or more fallback models on a different underlying provider (so a provider-wide outage doesn't take down both).
2. Wrap the MegaBrain call in retry logic that only fails over on retryable errors (5xx, timeout, 429) — not on 4xx validation errors.
3. Cap total fallback attempts (e.g. 2) and total wall-clock budget so a request doesn't hang indefinitely.
4. Log which model actually served each request so degraded-mode traffic is visible in monitoring.
5. Alert when fallback rate crosses a threshold (e.g. >5% of traffic in 10 minutes) — that signals a primary provider incident.

## Notes

- Keep the fallback model's output format close enough to the primary that downstream parsing doesn't break.
- Test the fallback path deliberately (e.g. via a feature flag) rather than only discovering it during a real outage.
