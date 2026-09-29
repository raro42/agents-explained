# Concept — thin agent loop

**Summary:** A timer-driven shell script moves work through markdown roles. Cursor is a step, not the system.

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

## Orchestrator

Public reference: [`pos-cursor-loop.sh`](https://github.com/satisfecho/pos/blob/master/agents2/pos-cursor-loop.sh).

## Related

- [Essay](essay-no-harness-works-best.md)
- [Local fallback](concept-local-fallback.md)
- [Decision models](concept-decision-models.md)
- [POS entity](entity-satisfecho-pos.md)
