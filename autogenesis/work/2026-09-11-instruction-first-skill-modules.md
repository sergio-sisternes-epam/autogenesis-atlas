---
type: work
title: Instruction-first modules for derived skills
created: 2026-09-11
work_id: 2026-09-11-instruction-first-skill-modules
status: done
description: Approved instruction-first guidance is implemented and locally validated; optional independent evaluation may add evidence, while GitHub CI remains the final release gate.
relates_to:
  - path: autogenesis/plans/2026-09-11-instruction-first-skill-modules.md
    kind: related
  - path: autogenesis/experiences/2026-09-11-python-tooling-overengineering-challenge.md
    kind: derived_from
  - path: autogenesis/work/2026-09-11-s8-core-profile-self-application.md
    kind: follows
  - path: autogenesis/experiences/2026-09-11-instruction-first-module-implementation.md
    kind: related
---

# Instruction-first modules for derived skills

## Scope

Define and teach useful skill-shaped modules without making derived skills
inherit a custom invocation framework or Python validators. Preserve separate
Autogenesis authoring discipline and repository release tooling.

## Status

The user selected simplification at 17:07, clarified downstream scope at 17:10
and requested "Proceed" at 17:13. Formal design re-entered from discussion.
The replacement packet was persisted and challenged, then explicitly approved
through "Approve implementation". The instruction changes and bounded
walkthrough are now present locally. acceptance was initially deferred because the private evaluator could not
import, independent evaluation launches were repeatedly killed, and GitHub CI
remained outstanding. The later evaluator-decoupling decision removed that
private tool from the Autogenesis runtime and implementation gates. Local
implementation is now done; optional independent evaluation may add evidence,
and GitHub CI remains the final release gate. S8 is still draft.

The user reiterated approval at 2026-09-11T18:21:20+01:00. Remaining local
release metadata, dependency, store and source-audit checks then passed. This
did not expand scope to the separate consumer-validator traversal defect.

The superseding evaluator-decoupling implementation passed 73 tests, all six
v4 smokes, the source contract, source audit, release/dependency/store
contracts, and both consumer profiles. This closes the local instruction-first
implementation without rewriting the earlier evaluation history.

## Outcomes

- [Implementation, actual evidence and explicit deferrals](../experiences/2026-09-11-instruction-first-module-implementation.md)
- [Superseding evaluator-decoupling evidence](../experiences/2026-09-11-evaluator-decoupling-implementation.md)
- [Replacement design and approval boundary](../plans/2026-09-11-instruction-first-skill-modules.md)
- [Source-grounded challenge and corrected scope](../experiences/2026-09-11-python-tooling-overengineering-challenge.md)
- [Earlier proposal, now deferred](../plans/2026-09-11-s8-core-profile-self-application.md)
