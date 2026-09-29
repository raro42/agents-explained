# AGENTS — agents-explained (Karpathy LLM Wiki)

Schema for this repository. Follow on every ingest, query, and lint.

Pattern: [Karpathy LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

## Purpose

Public write-up of a **thin agent loop**: shell orchestrator, local decisions, cloud coder as a worker. Linked from X / blog. Proof comes from public repos.

## Layers

| Layer | Path | Rule |
|-------|------|------|
| Raw sources | `raw/` | Immutable. Screenshots, issue exports, log tails. LLM reads only. |
| Wiki | `wiki/` + essay at root via README | LLM may create/update markdown here |
| Schema | this file | Binding for agents in this repo |

## Special files (mandatory)

| File | Role |
|------|------|
| [index.md](index.md) | Catalog — update on every ingest |
| [log.md](log.md) | Append-only timeline |
| [README.md](README.md) | Public front door + essay entry |

## Hard rules

| Rule | Detail |
|------|--------|
| No customer internals | Private customer loops: one sentence only. No host names, no stack maps, no ops runbooks from private repos. |
| Public proof first | Prefer `satisfecho/pos`, `raro42/mac-stats`, `raro42/ai-stock-checker`. |
| STE prose | Short sentences. Active voice. No filler. |
| License | MIT. Contributions via **GitHub Issues** only (see [CONTRIBUTING.md](CONTRIBUTING.md)). |

## Operations

**Ingest.** Drop evidence under `raw/`. Summarize into `wiki/`. Update `index.md`. Append `log.md`.

**Query.** Read `index.md` first. Cite paths. File strong answers back into the wiki.

**Lint.** Check contradictions, orphans, stale counts, customer leakage. Append a `lint` entry to `log.md`.

## Log format

```text
## [YYYY-MM-DD] kind | Title
```

Kinds: `ingest` | `query` | `lint` | `schema` | `essay`.
