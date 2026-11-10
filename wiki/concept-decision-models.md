# Concept — decision models (Laya-shaped)

**Summary:** Classification and gates need typed labels, not chat prose. We are integrating [Laya](https://github.com/NandhaKishorM/laya) as the decision plane: **tool coordinator** before the worker, **answer quality gate** after it.

## Public references

| Item | Link |
|------|------|
| Laya (open, Apache 2.0) | https://github.com/NandhaKishorM/laya |
| Weights | https://huggingface.co/convaiinnovations/laya |
| PyPI | https://pypi.org/project/laya/ |
| Docs | https://laya.studio/docs |
| Jev vs Laya article | https://dev.to/jamilxt/jev-vs-laya-the-same-ai-idea-one-closed-and-one-open-3c6e |
| Jev (closed API) | https://typesafe.ai |

## Two jobs in the loop

Laya does **not** write chat or code. It decides. Cursor / Claude Code / OpenCode / a local LLM generate.

| Job | When | Shape | Outcome |
|-----|------|-------|---------|
| **Tool coordinator** | After shell preflight, before the generative worker | Choice (next tool / action / skip / escalate); optional Noul for tool risk | Spawn coder, tester, search, refuse, or park |
| **Answer quality gate** | After the worker returns text or a result | Score or Bool (keep / repair / reopen) | Pass, one repair, or reopen |

```text
issue / ask
  → shell preflight
  → Laya tool coordinator (label + confidence)
       └─ low confidence → rules / Ollama fallback
  → generative worker
  → Laya answer quality gate
       └─ miss → one repair, then keep or reopen
```

## Decision shapes

| Decision | Shape |
|----------|--------|
| Next tool / action / skip / escalate | Choice |
| Command or tool call looks risky | Noul |
| New issue → FEAT / skip / wait human | Choice |
| Log line → SKIP / ESCALATE | Choice |
| Answer / test result → keep / repair / reopen | Score or Bool |
| Confidence too low | Shell / rules fallback (fail-open) |

## Adoption rules

1. **Shadow first.** Log Laya labels beside rules. Do not block until the bench is green.
2. **Fail-open.** Below a confidence floor, use shell rules or Ollama. Do not stall the loop.
3. **Self-host for private data.** Closed cloud classifiers add egress risk.
4. Public product trees may still use Ollama for triage until Laya clients land. Same roles; swap the head later.

We also use the same decision-plane idea on a private customer loop. No internals here.

## Related

- [Essay](essay-no-harness-works-best.md)
- [Agent loop](concept-agent-loop.md)
- [Local fallback](concept-local-fallback.md)
