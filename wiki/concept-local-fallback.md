# Concept — local control plane + cloud worker

**Summary:** Keep triage and gating on the machine. Use cloud models only for hard coding.

## Why it matters

Overlapping cloud AI outages (e.g. September 2026) showed that “agent = one vendor API” fails together. A shell loop with Ollama triage still:

- runs preflight
- skips empty queues
- stamps last-review times
- drafts SKIP / ESCALATE on logs

Coder quality drops when Cursor’s upstream models degrade. The **factory** does not vanish.

## POS defaults (public docs)

- `AGENT_001_LOCAL_LOG_REVIEWER` — avoid Cursor for log-only noise when GitHub queue is empty  
- `scripts/agent-ollama-log-triage.sh` — Ollama first, optional llama.cpp fallback  
- Stamp-only dirty trees — no committer burn

Detail: POS [`docs/agent-loop.md`](https://github.com/satisfecho/pos/blob/master/docs/agent-loop.md).

## Related

- [Essay](essay-no-harness-works-best.md)
- [Decision models](concept-decision-models.md)
