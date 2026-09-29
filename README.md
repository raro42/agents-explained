# agents-explained

**No harness works best for me.**

Meaning: no agent framework. The loop is bash, folder names, and gh. Cursor is a worker.

Coder slot is swappable: Cursor, Claude Code, OpenCode — whatever can edit the tree. The loop does not care.

→ **Essay:** [wiki/essay-no-harness-works-best.md](wiki/essay-no-harness-works-best.md)

## What to copy

1. One shell orchestrator on a timer.
2. Role prompts as markdown.
3. Task files as the only queue (`FEAT` → `WIP` → `UNTESTED` → `TESTING` → `CLOSED`).
4. Preflight before every paid agent call.
5. Local model for triage; Cursor only for hard edits.

## Proof

HammyHavoc filed a large batch on [satisfecho/pos](https://github.com/satisfecho/pos). **36 closed**, **0 open** at capture (2026-09-29). Trail for [#391](https://github.com/satisfecho/pos/issues/391): reviewer → coder → tester → close.

Full write-up: [wiki/proof-hammyhavoc.md](wiki/proof-hammyhavoc.md).

## Same pattern elsewhere

| Repo | Link |
|------|------|
| POS `agents2/` | https://github.com/satisfecho/pos/tree/master/agents2 |
| mac-stats `agents/` | https://github.com/raro42/mac-stats/tree/main/agents |
| ai-stock-checker | https://github.com/raro42/ai-stock-checker/blob/main/AGENTS.md |

## License and contribute

- **License:** [MIT](LICENSE)
- **Contribute:** [GitHub Issues](https://github.com/raro42/agents-explained/issues) only — see [CONTRIBUTING.md](CONTRIBUTING.md)

## Layout

| Path | Role |
|------|------|
| `raw/` | Immutable sources and screenshots |
| `wiki/` | Essay, concepts, proof |
| `AGENTS.md` | Schema for agents that maintain this wiki |
| `index.md` | Catalog |
| `log.md` | Timeline |

Pattern: [Karpathy llm-wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).
