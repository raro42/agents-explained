# Concept — tried the harnesses

**Summary:** “No harness” is earned. Big agent products were tried; thin shell stayed.

## What was tried (public story)

| System | Note |
|--------|------|
| pi / [pi.dev](https://pi.dev) | Local-agent product surface |
| OpenCode | Agent-in-a-box; release-coupled control flow |
| Hermes | Useful components; not a full issue factory |
| OpenClaw (flavors) | Heavy; updater / breakage risk |
| In-repo harness (mac-stats) | Grew holes; cut back toward shell + markdown |

## Thesis

Harnesses are large. They hide control flow. They break on their own schedule. Prefer a timer, role markdown, and task files you can `ls`.

## Related

- [Essay](essay-no-harness-works-best.md)
- [Agent loop](concept-agent-loop.md)
- [mac-stats](entity-mac-stats.md)
