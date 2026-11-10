# Concept — thin agent loop

**Summary:** A timer-driven shell script moves work through markdown roles. Cursor is a step, not the system. [Laya](https://github.com/NandhaKishorM/laya) sits in two decision slots around the generative worker.

## Stages (POS naming)

| Step | Role | Typical output |
|------|------|----------------|
| 001 | GitHub / log reviewer | `FEAT-*.md` or `NEW-*.md` |
| 006 / 010 | Feature coder | Code + `UNTESTED-*.md` |
| 002 | Main coder | Same for log incidents |
| 003 | Tester | Pass → `CLOSED-`; fail → `WIP-` |
| 004 / 030 | Closing reviewer | Archive under `done/YYYY/MM/DD/` |
| 007 / 040 | Committer | Changelog, commit, issue comments |
| 009 | Promote | Optional `development` → `master` cadence |

## Decision slots ([Laya](https://github.com/NandhaKishorM/laya))

| Slot | Placement | Job |
|------|-----------|-----|
| Tool coordinator | After shell preflight, before 006 / 010 / 002 (and similar workers) | Choice: next tool / action / skip / escalate |
| Answer quality gate | After 003 (or other generative result), before close / archive | Score or Bool: keep / one repair / reopen |

Low confidence → rules or Ollama. [Laya](https://github.com/NandhaKishorM/laya) does not generate code. See [decision models](concept-decision-models.md).

## Orchestrator

Public reference: [`pos-cursor-loop.sh`](https://github.com/satisfecho/pos/blob/master/agents2/pos-cursor-loop.sh).

## Related

- [Essay](essay-no-harness-works-best.md)
- [Local fallback](concept-local-fallback.md)
- [Decision models](concept-decision-models.md)
- [POS entity](entity-satisfecho-pos.md)
