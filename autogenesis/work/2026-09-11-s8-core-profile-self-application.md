---
type: work
title: S8 core and Autogenesis profile self-application
created: 2026-09-11
work_id: 2026-09-11-s8-core-profile-self-application
status: deferred
description: Earlier machinery-heavy proposal retained as history; replaced by the instruction-first derived-skill design.
relates_to:
  - path: autogenesis/work/2026-09-11-instruction-first-skill-modules.md
    kind: related
  - path: autogenesis/experiences/2026-09-11-python-tooling-overengineering-challenge.md
    kind: related
  - path: autogenesis/plans/2026-09-11-s8-core-profile-self-application.md
    kind: related
  - path: autogenesis/experiences/2026-09-11-s8-self-review-diagnostic.md
    kind: derived_from
  - path: autogenesis/work/2026-09-11-parent-routed-skill-module-pattern.md
    kind: follows
---

# S8 core and profile self-application

## Scope

Formalize the portable S8 contract and the Autogenesis-specific profile;
repair D1-D8 through explicit module interfaces and evidence-tiered diagnostics.
No product edits until approval of the persisted plan.

## Status

The earlier core/profile direction was approved after the S8 diagnostic, but
its implementation packet was never approved. It is now deferred in favour of
the instruction-first derived-skill design; do not implement it as written.
Prior S8 and module-migration acceptance remains deferred independently.

At 17:07 +01:00 the user selected the instruction-first simplification
direction. At 17:10 the user clarified its scope: the design discipline passed
to skills created or evolved through Autogenesis, not this repository's release
support scripts. The machinery-heavy packet needs reconsideration rather than
implementation as written. Whether to delete existing release safeguards is
not the live design question.

## Outcomes

- [Replacement work](2026-09-11-instruction-first-skill-modules.md) - designed; implementation approval pending
- [Python tooling complexity challenge](../experiences/2026-09-11-python-tooling-overengineering-challenge.md) - simplify the discipline inherited by derived skills; repository release tooling is a separate concern
- [Formal design and approval gate](../plans/2026-09-11-s8-core-profile-self-application.md)
- [Diagnostic, proposed standard and all-21 assessment](../experiences/2026-09-11-s8-self-review-diagnostic.md)
