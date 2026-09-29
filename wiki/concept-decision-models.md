# Concept — decision models (Laya-shaped)

**Summary:** Classification and gates need typed labels, not chat prose.

## Public references

| Item | Link |
|------|------|
| Laya (open, Apache 2.0) | https://github.com/NandhaKishorM/laya |
| Weights | https://huggingface.co/convaiinnovations/laya |
| PyPI | https://pypi.org/project/laya/ |
| Docs | https://laya.studio/docs |
| Jev vs Laya article | https://dev.to/jamilxt/jev-vs-laya-the-same-ai-idea-one-closed-and-one-open-3c6e |
| Jev (closed API) | https://typesafe.ai |

## Fit in the loop

| Decision | Shape |
|----------|--------|
| New issue → FEAT / skip / wait human | Choice |
| Log line → SKIP / ESCALATE | Choice |
| Test outcome → close / reopen | Bool or Choice |
| Confidence too low | Rules fallback |

Prefer **self-hosted** decision heads for customer data. Closed cloud classifiers add egress risk.

## Related

- [Essay](essay-no-harness-works-best.md)
- [Local fallback](concept-local-fallback.md)
