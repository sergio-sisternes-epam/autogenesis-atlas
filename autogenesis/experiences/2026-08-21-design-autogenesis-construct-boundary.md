---
type: experience
title: "DESIGN: Autogenesis \u2194 construct boundary (no cycles)"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "R1\u2013R5 acyclic deps; ownership matrix; post-implement construct gate; activation vs discipline placement. Plan autogenesis-construct-boundary-2026-08-21."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/challenge-adversarial-construct.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-design-autogenesis-construct-boundary`.

## What happened

**Plan:** `artifacts/autogenesis-plans/autogenesis-construct-boundary-2026-08-21.md`

- construct MUST NOT depend on autogenesis
- autogenesis MAY call construct CLI after implement
- activation SoT = construct when workspace exists
- discipline = path rules + structural smokes subset
- completion gated by construct when scenario covers change

Status: stop for approve

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
