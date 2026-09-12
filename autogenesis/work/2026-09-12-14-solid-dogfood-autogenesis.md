---
type: work
title: Dogfood the SOLID lens on Autogenesis
created: 2026-09-12
work_id: 2026-09-12-14-solid-dogfood-autogenesis
status: done
external_ref: sergio-sisternes-epam/autogenesis#14
description: Apply the approved skill-native SOLID lens to Autogenesis itself before the next release, with workspace-source evaluation and comparative design evidence, without absorbing the lens PR.
relates_to:
  - path: autogenesis/plans/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: related
  - path: autogenesis/work/2026-09-12-solid-skill-design-lens.md
    kind: follows
  - path: autogenesis/experiences/2026-09-12-solid-skill-design-lens-implementation.md
    kind: derived_from
  - path: autogenesis/experiences/2026-09-12-14-solid-lens-self-analysis.md
    kind: related
  - path: autogenesis/experiences/2026-09-12-14-solid-improvement-recommendations.md
    kind: related
  - path: autogenesis/experiences/2026-09-12-14-solid-dogfood-implementation.md
    kind: related
---

# Dogfood the SOLID lens on Autogenesis

## Scope

Use the shipped SOLID authority against Autogenesis before the next version
cut. First slice: prove the current branch is the skill under test, then run
three comparative design exercises that show the lens changing a design
decision. Deferred items stay protostars beside the plan.

## Status

Explicit implement approval received. First slice is implemented from workspace
Autogenesis v0.6.0 with workspace-source fail-closed checks, three comparative
exercises, current-suite adversarial smokes, and docs. Catalog v0.4.3 was not
evidence. Parked protostars remain unimplemented.

## Outcomes

- [Design plan awaiting approval](../plans/2026-09-12-14-solid-dogfood-autogenesis.md)
- [Self-analysis of Autogenesis through the lens](../experiences/2026-09-12-14-solid-lens-self-analysis.md)
- [Ranked improvement recommendations](../experiences/2026-09-12-14-solid-improvement-recommendations.md)
- [This design run](../experiences/2026-09-12-14-solid-dogfood-design.md)
- [Implement experience](../experiences/2026-09-12-14-solid-dogfood-implementation.md)
- Prerequisite lens work remains [2026-09-12-solid-skill-design-lens](2026-09-12-solid-skill-design-lens.md)

## Related

GitHub tracker for this work is the linked issue on the Autogenesis repository.
The lens implementation lives on pull request 11 and must stay a separate
change set.
