---
name: project-docs-maintenance
description: Keep project docs aligned with current code truth and confirmed target architecture. Use after code or design changes, docs drift, review findings, evaluation findings, or a docs Task.
---

# Project Docs Maintenance

Keep stable docs trustworthy without blending what exists with what is intended.

## Read Path

Read:

1. docs navigation and project map
2. architecture overview and the touched boundary page
3. the confirmed PRD, Issue, Task, ADR, review, or evaluation
4. current code, config, and tests needed to verify the claim

Do not treat old plans or agent summaries as truth.

## Truth

For current behavior, trust current code, runtime configuration, and focused
tests.

For target architecture, trust confirmed target docs and ADRs. A confirmed PRD,
Issue, or Task may refine its own scope but must not silently contradict the
project's target docs.

When current and target disagree, describe the Migration Gap. When two
confirmed target sources disagree, report the contradiction instead of
choosing one silently.

## Role Modes

- **Talk:** update target docs after human confirmation.
- **Implementation and Debug:** make preliminary factual updates and write a
  Docs Impact section.
- **Code Review:** audit Task-level docs completeness; report binding findings
  without repairing the docs being judged.
- **Evaluation:** audit system-level alignment; withhold pass on material drift.

Run roles never ask the human directly. A material unresolved contradiction
becomes a typed decision request.

## Edit When

Edit stable docs when:

- public behavior or a contract changed
- a confirmed decision changed target architecture
- docs contradict code, config, tests, or confirmed target truth
- the active Task owns docs work

Keep narrow Tasks narrow. Otherwise write Docs Impact and let the next owning
gate decide.

## Docs Impact

```text
Docs Impact
- Stable docs changed:
- Stable docs likely need update:
- Current-code fact changed:
- Target architecture changed:
- Migration gap changed:
- Contradiction or decision needed:
```

## Completion

The next fresh agent must be able to orient from the docs without mistaking
target design for implemented behavior.

Read [references/docs-audit.md](references/docs-audit.md) in Review or
Evaluation mode.

