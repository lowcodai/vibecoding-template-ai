# vibecoding-template-ai

> Template for AI, agent, MCP, prompt, RAG, and LLM projects.

[![Governance](https://img.shields.io/badge/governance-lowcodai-blue)](https://github.com/lowcodai/vibecoding-copilot-governance)

## Description

GitHub template for lowcodai artificial intelligence projects. Includes everything from `vibecoding-template-base` plus:
- Agents, prompts, MCP, and RAG structure
- AI governance instructions (safety, prompt engineering)
- AI-specific hooks (session-logger, attester-import-check)
- AI Safety Check workflow
- AI-specific Awesome Copilot elements (acreadiness, arize, agentic-eval…)

## Agent rulebook

[`AGENTS.md`](AGENTS.md) is the first file every agent (Hermes, Claude Code, Copilot) and every
contributor reads: commands, repository map, the DEV → REVIEW → TEST workflow (ADR-0005),
boundaries and definition of done. Fill in its `TODO` markers when you create a project from
this template. It is rendered by `vibecoding-bootstrap/scripts/apply-template.sh`, the single
source for all templates — change the generator, then re-render, rather than editing one copy.
The orchestration files it refers to (`.ai/`, `.claude/`, `scripts/orchestrate.py`) are
installed by `vibecoding-bootstrap/scripts/sync-governance.sh`.

## Usage

```bash
cd vibecoding-bootstrap
./scripts/new-project.sh --type ai --name <my-ai-project>
```

## AI-specific structure

```
.
├── agents/     # .agent.md files — agent definitions
├── prompts/    # Versioned prompts with metadata
├── mcp/        # MCP servers (Model Context Protocol)
├── rag/        # RAG pipelines (chunking, indexing, retrieval)
└── llm-wiki/   # Documentation of models and observed behaviors
```

## AI Safety & Governance

All AI projects must comply with the `ai-usage-policy.md` policy from lowcodai governance.

Before every merge:
1. Review prompts with `ai-prompt-engineering-safety-review`
2. Validate agents with `agent-governance`
3. Check OWASP LLM Top 10 compliance via `agent-owasp-compliance`

## AI-specific Awesome Copilot elements

| Element | Type | Usage |
|---------|------|-------|
| `agent-safety.instructions.md` | Instruction | Safety for agents |
| `ai-prompt-engineering-safety-best-practices.instructions.md` | Instruction | Prompt safety |
| `acreadiness-assess` | Skill | AI maturity assessment |
| `agent-governance` | Skill | Agent governance |
| `agentic-eval` | Skill | Agent behavior evaluation |
| `ai-prompt-engineering-safety-review` | Skill | Prompt safety review |
| `agent-owasp-compliance` | Skill | OWASP LLM compliance |
| `arize-instrumentation` | Skill | LLM observability |
| `acreadiness-cockpit` | Plugin | AI maturity dashboard |

## Hooks

This repo's AI-specific hooks:

| Hook | Usage |
|------|-------|
| `session-logger` | Logs AI/Copilot session activity |
| `attester-import-check` | Verifies supply-chain import provenance |

See `.github/copilot-instructions.md` for this repo's full active hooks list, and the [governance hooks registry](https://github.com/lowcodai/vibecoding-copilot-governance/blob/main/docs/awesome-copilot-map.md) for the full ecosystem-wide catalog.

## References

- [vibecoding-copilot-governance](https://github.com/lowcodai/vibecoding-copilot-governance)
- [OWASP LLM Top 10](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [github/awesome-copilot](https://github.com/github/awesome-copilot)
