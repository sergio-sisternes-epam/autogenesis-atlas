---
type: experience
title: "Implement: plan home moved to subject Atlas with initiate/migrate offers"
created: 2026-08-23
work_id: autogenesis-plan-home-subject-atlas-v1
status: done
description: "v0.3.3 discipline: plans in subject Atlas; missing Atlas informs user and offers initiate; okf-wiki also offers migrate."
relates_to:
  - path: autogenesis/work/autogenesis-plan-home-subject-atlas-v1.md
    kind: implements
  - path: autogenesis/decisions/plan-home-is-subject-atlas.md
    kind: records
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: follows
---

## Context

User requested Autogenesis store plans inside the Atlas of the target skill/path; if no Atlas, inform and offer initiate; if okf-wiki found, also offer migration.

## What happened

Updated SKILL.md (v0.3.3), workflow-discipline (plan home + Subject Atlas resolution table), design.md, initialise.md, reevaluate.md. Recorded decision and this experience.

## Outcome

Discipline encodes the contract. Agents must not silent-write plans to artifacts/autogenesis-plans/.

## Changed files

- SKILL.md
- references/modules/workflow-discipline.md
- references/paths/design.md
- references/paths/initialise.md
- references/paths/reevaluate.md
- references/atlas/decisions/plan-home-is-subject-atlas.md
- references/atlas/work/autogenesis-plan-home-subject-atlas-v1.md
