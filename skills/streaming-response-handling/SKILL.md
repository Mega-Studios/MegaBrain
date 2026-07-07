---
name: streaming-response-handling
description: Implement robust SSE streaming for chat completions through MegaBrain's OpenAI-compatible gateway, including partial-token handling and clean cancellation. Use when building a chat UI or CLI.
metadata:
  category: integration
  product: megabrain
---

# Streaming Response Handling

## When to Use This Skill

- Building a chat interface that should render tokens as they arrive
- Debugging truncated or garbled streamed output

## Steps

1. Set `stream: true` on the MegaBrain chat completions request and read the response as Server-Sent Events.
2. Parse each `data:` line as a JSON delta; concatenate `choices[0].delta.content` fragments in arrival order.
3. Handle the terminal `data: [DONE]` sentinel explicitly — don't rely on the connection simply closing.
4. Support client-initiated cancellation by aborting the underlying HTTP request, and confirm MegaBrain stops billing once the stream is closed.
5. Handle mid-stream errors (a provider timeout after the first tokens arrived) by surfacing a partial-result state to the UI instead of silently dropping content.
6. Test with at least one model that streams tool-call arguments incrementally, since delta shapes differ slightly from plain text deltas.

## Notes

- Buffer on newline/JSON boundaries, not on a fixed byte size — SSE chunks don't align to message boundaries.
- Never block the UI thread parsing deltas; process them incrementally.
