# agents-explained

**No harness works best for me.**

Public wiki + essay on thin agent loops: shell orchestrator, local triage, Cursor as a worker.

→ **Read the essay:** [wiki/essay-no-harness-works-best.md](wiki/essay-no-harness-works-best.md)

## Why this repo

I use the same pattern across public products and (without internals) on private customer work:

| Example | Link |
|---------|------|
| POS agents | https://github.com/satisfecho/pos/tree/master/agents2 |
| mac-stats agents | https://github.com/raro42/mac-stats/tree/main/agents |
| Stock checker | https://github.com/raro42/ai-stock-checker/blob/main/AGENTS.md |

Proof batch: **HammyHavoc** filed dozens of issues on `satisfecho/pos`; **36 closed** at capture (2026-09-29). See [wiki/proof-hammyhavoc.md](wiki/proof-hammyhavoc.md).

## Layout (Karpathy LLM Wiki)

| Path | Role |
|------|------|
| `raw/` | Immutable sources and screenshots |
| `wiki/` | Compiled pages (essay, concepts, entities) |
| `AGENTS.md` | Schema for agents maintaining this wiki |
| `index.md` | Catalog |
| `log.md` | Timeline |

Pattern: [Karpathy llm-wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

## License and contribute

- **License:** [MIT](LICENSE)
- **Contribute:** [GitHub Issues](https://github.com/raro42/agents-explained/issues) — see [CONTRIBUTING.md](CONTRIBUTING.md)
