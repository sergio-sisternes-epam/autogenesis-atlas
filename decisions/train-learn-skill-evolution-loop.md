---
type: decision
title: "Train / Learn / skill-evolution loop"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Migrated knowledge: Train / Learn / skill-evolution loop"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

| Path | Role |
|------|------|
| **Learn** (agent-brain) | Encode knowledge. No same-run package mutation. Feeds **reevaluate proposals** after material change. |
| **Train** (agent-brain) | Progressive **practice** (domain default). Optional: practice autogenesis discipline as meta curriculum. |
| **reevaluate** (autogenesis) | Transfer signal → structured skill-update proposals only. |
| **design / implement / PR** | Gated skill-package evolution. |

“Does not evolve skills” = no **unattended mutation**, not no **proposals**.

## Rationale

Migrated from okf-wiki knowledge page `train-learn-skill-evolution-loop` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
