---
name: byok-provider-setup
description: Configure bring-your-own-key (BYOK) providers inside a MegaBrain account so enterprise traffic routes through the customer's own provider contracts/quotas. Use for enterprise or compliance-driven setups.
metadata:
  category: administration
  product: megabrain
---

# BYOK Provider Setup

## When to Use This Skill

- An enterprise customer already has direct contracts/quota with a provider and wants to keep using them through MegaBrain's unified API
- Compliance requires traffic to run under the customer's own provider account for audit or data-residency reasons

## Steps

1. Confirm which providers the customer wants to bring their own key for, and collect the credentials through MegaBrain's secure key storage (never paste keys into chat/plaintext channels).
2. Register each BYOK credential against the correct project/team scope so it isn't shared across unrelated workloads.
3. Configure routing so requests for that provider's models use the BYOK credential instead of MegaBrain's pooled capacity.
4. Verify billing now flows to the customer's own provider account for BYOK models, while MegaBrain-pooled models remain on the standard plan.
5. Set an expiry/rotation reminder for the provided keys.

## Notes

- Treat BYOK credentials as customer secrets — least-privilege scoping and rotation reminders are not optional.
- Document which models are BYOK vs. pooled so cost/ownership stays clear during incident response.
