# MegaBrain — Public Skills, MCPs & Agents

[MegaBrain](https://getmegabrain.com) is an AI gateway giving access to 500+ models (Claude, GPT, Gemini, Llama, and more) through a single OpenAI-compatible API.

This repo is a curated marketplace of **Skills**, **MCP Servers**, and **Agents** for using MegaBrain effectively with AI coding agents (Claude Code, Cline, and other compatible clients), following the structure of the [Kilo Marketplace](https://github.com/Kilo-Org/kilo-marketplace).

| Resource | Description |
|----------|--------------|
| **[Skills](#skills)** | Modular workflows for tasks like model routing, cost optimization, and migration onto MegaBrain |
| **[MCP Servers](#mcp-servers)** | MCP tools for calling MegaBrain's gateway, usage/billing, model catalog, and admin APIs |
| **[Agents](#agents)** | Focused agent configurations for MegaBrain-related engineering and ops tasks |

---

## Skills

Each skill is a folder containing a `SKILL.md` file with YAML frontmatter and instructions, following the open [Agent Skills specification](https://agentskills.io/):

```
skills/
└── skill-name/
    └── SKILL.md
```

| Skill | Description |
|-------|--------------|
| [model-router-strategy](skills/model-router-strategy/SKILL.md) | Design a routing strategy across MegaBrain's 500+ models balancing cost, latency, and quality |
| [megabrain-cost-optimizer](skills/megabrain-cost-optimizer/SKILL.md) | Analyze MegaBrain spend and recommend concrete cost cuts |
| [openai-compatible-migration](skills/openai-compatible-migration/SKILL.md) | Migrate an OpenAI-SDK codebase onto MegaBrain's gateway |
| [multi-model-fallback](skills/multi-model-fallback/SKILL.md) | Automatic failover across models/providers behind MegaBrain |
| [prompt-ab-testing](skills/prompt-ab-testing/SKILL.md) | Compare the same prompt across multiple models to pick the best one |
| [megabrain-usage-analytics](skills/megabrain-usage-analytics/SKILL.md) | Pull and analyze usage/spend data from MegaBrain |
| [streaming-response-handling](skills/streaming-response-handling/SKILL.md) | Robust SSE streaming for chat completions through MegaBrain |
| [rate-limit-resilience](skills/rate-limit-resilience/SKILL.md) | Handle 429s and backoff across providers behind MegaBrain |
| [model-benchmarking](skills/model-benchmarking/SKILL.md) | Benchmark candidate models on latency, cost, and quality |
| [byok-provider-setup](skills/byok-provider-setup/SKILL.md) | Configure bring-your-own-key providers for enterprise routing |

---

## MCP Servers

Each MCP server is a folder containing an `MCP.yaml` manifest:

```
mcps/
└── server-name/
    └── MCP.yaml
```

| MCP Server | Description |
|------------|--------------|
| [megabrain-gateway](mcps/megabrain-gateway/MCP.yaml) | Call any MegaBrain model through a single OpenAI-compatible MCP tool |
| [megabrain-usage](mcps/megabrain-usage/MCP.yaml) | Query MegaBrain usage and billing data |
| [megabrain-model-catalog](mcps/megabrain-model-catalog/MCP.yaml) | Search MegaBrain's catalog of 500+ models |
| [megabrain-keys](mcps/megabrain-keys/MCP.yaml) | Create, list, and revoke MegaBrain API keys |
| [megabrain-router](mcps/megabrain-router/MCP.yaml) | Read and update routing rules and fallback chains |
| [megabrain-webhooks](mcps/megabrain-webhooks/MCP.yaml) | Manage webhook subscriptions for usage/spend alerts |
| [megabrain-eval](mcps/megabrain-eval/MCP.yaml) | Run a prompt across multiple models in one call |
| [megabrain-cache](mcps/megabrain-cache/MCP.yaml) | Configure prompt/response caching |
| [megabrain-teams](mcps/megabrain-teams/MCP.yaml) | Manage team members, roles, and permissions |
| [megabrain-logs](mcps/megabrain-logs/MCP.yaml) | Query request logs and traces for debugging |

---

## Agents

Each agent is a folder containing an `AGENT_DEFINITION.md` file with YAML frontmatter and instructions:

```
agents/
└── agent-name/
    └── AGENT_DEFINITION.md
```

| Agent | Description |
|-------|--------------|
| [model-selection-advisor](agents/model-selection-advisor/AGENT_DEFINITION.md) | Recommends which model(s) fit a task on cost/latency/quality |
| [cost-guardian](agents/cost-guardian/AGENT_DEFINITION.md) | Monitors spend and flags expensive or wasteful calls |
| [migration-specialist](agents/migration-specialist/AGENT_DEFINITION.md) | Migrates codebases onto MegaBrain's gateway |
| [prompt-evaluator](agents/prompt-evaluator/AGENT_DEFINITION.md) | Runs and judges prompt/model comparisons |
| [integration-engineer](agents/integration-engineer/AGENT_DEFINITION.md) | Builds new integrations against MegaBrain's API |
| [reliability-engineer](agents/reliability-engineer/AGENT_DEFINITION.md) | Designs retry/failover strategy across models |
| [usage-analyst](agents/usage-analyst/AGENT_DEFINITION.md) | Analyzes usage data and produces reports |
| [onboarding-guide](agents/onboarding-guide/AGENT_DEFINITION.md) | Walks new users through first MegaBrain call |
| [security-reviewer](agents/security-reviewer/AGENT_DEFINITION.md) | Reviews API key handling and secrets hygiene |
| [docs-writer](agents/docs-writer/AGENT_DEFINITION.md) | Writes MegaBrain integration guides and docs |

---

## Cline Skills (legacy)

The custom-instruction skills below predate the marketplace structure above and remain available for [Cline](https://github.com/cline/cline) users. Paste one into Cline's **Custom Instructions** field.

| Skill | Description |
|-------|-------------|
| [MegaBrain Design System](skills/mds-design-system.md) | Creates HTML/CSS output matching MegaBrain's visual identity — dark backgrounds, brand orange, clean typography |
| [McKinsey 7-Step + Pyramid Principle](skills/mckinsey-7-step.md) | Structures data analysis using McKinsey's 7-step framework and presents findings using the Pyramid Principle |

---

## Links

- **Docs:** [getmegabrain.com/docs](https://getmegabrain.com/docs)
- **Skills page:** [getmegabrain.com/docs/skills](https://getmegabrain.com/docs/skills)
- **Models:** [getmegabrain.com/models](https://getmegabrain.com/models)
- **Book a setup session:** [getmegabrain.com/book](https://getmegabrain.com/book)
