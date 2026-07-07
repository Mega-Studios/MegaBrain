---
name: rate-limit-resilience
description: Handle 429 rate-limit responses and backoff across the many providers reachable through MegaBrain's single gateway. Use when a user reports intermittent failures under load.
metadata:
  category: reliability
  product: megabrain
---

# Rate-Limit Resilience

## When to Use This Skill

- Requests intermittently fail with 429 during traffic spikes
- A user wants to raise safe concurrency without tripping provider-side limits

## Steps

1. Confirm the 429 originates from the upstream provider (surfaced through MegaBrain) rather than a MegaBrain-side account limit — check the error body/headers.
2. Implement exponential backoff with jitter, respecting a `Retry-After` header when present.
3. Add a request queue or token-bucket limiter client-side sized to the account's actual throughput ceiling, rather than retrying blindly.
4. Where sustained throughput is the real need, spread load across multiple models/providers (see `multi-model-fallback`) instead of only retrying the same one.
5. Alert when 429 rate exceeds a threshold — it usually means real traffic has outgrown the current plan/limits, not just a transient blip.

## Notes

- Don't retry non-idempotent side-effecting calls (e.g. ones that trigger downstream actions) without dedup protection.
- Cap total retry time so a user-facing request fails fast instead of hanging.
