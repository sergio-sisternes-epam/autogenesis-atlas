---
type: experience
title: "Autogenesis-aware runtime design with governance folded"
created: 2026-08-16
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Migrated experience: Autogenesis-aware runtime design with governance folded"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/challenge-adversarial-construct.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-16-aware-runtime-governance`.

## What happened

Genesis plan for making generated skills Autogenesis-aware at runtime, after think-challenge and with governance added:

`artifacts/autogenesis-plans/autogenesis-aware-runtime-plan-2026-08-16.md`

Key governance now required:
- provenance + status: unverified on every runtime experience
- hard write budget
- cheap dedup
- pruning / active forgetting
- safety-sensitive mode
- absolute “never implement” rule

Cost stance remains frugal.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
