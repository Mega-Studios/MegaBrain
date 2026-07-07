---
name: openai-compatible-migration
description: Migrate an existing codebase that calls the OpenAI API (or another single-provider SDK) onto MegaBrain's OpenAI-compatible gateway with minimal code changes. Use when a user wants access to 500+ models without rewriting their integration.
metadata:
  category: migration
  product: megabrain
---

# OpenAI-Compatible Migration

## When to Use This Skill

- A codebase already uses the official OpenAI SDK (Python, Node, or raw HTTP) and wants to add Claude/Gemini/Llama/etc. without a rewrite
- Consolidating multiple provider SDKs behind one client

## Steps

1. Locate every place the OpenAI client is instantiated (`base_url`, `api_key`).
2. Point `base_url` at MegaBrain's endpoint and swap in a MegaBrain API key — the request/response shape is unchanged.
3. Replace hardcoded model strings (e.g. `gpt-4o`) with MegaBrain model identifiers for the desired provider/model.
4. Verify streaming, function/tool calling, and structured output still work identically, since MegaBrain preserves the OpenAI wire format.
5. Remove now-redundant provider-specific SDKs once all call sites are migrated.
6. Add a smoke test that calls at least two different underlying providers through the same client code path.

## Notes

- No client library changes are required — this is purely a `base_url`/`api_key`/`model` swap.
- Keep provider-specific quirks (e.g. differing max output tokens) documented next to the model config.
