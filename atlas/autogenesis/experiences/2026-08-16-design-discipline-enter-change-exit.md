---
type: experience
title: "2026-08-16 Design: Enter|Change|Exit discipline simplification"
created: 2026-08-16
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Design rationale for autogenesis adherence: activation card, three clusters, lineage\u2192okf-wiki, path receipt."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-16-design-discipline-enter-change-exit`.

## What happened

## Problem
Agents adhere to **genesis** well (diagrams-before-body) but skip autogenesis gates when they are many, late, or satisfied by `validate` alone. Lineage was treated as a markdown file, not an okf-wiki activation.

## Design
Collapse public blockers to **Enter → Change → Exit**:

1. **Enter** — activation card first (mode, subject, path, path_module must-load, intent).
2. **Change** — design uses genesis path; implement only after explicit approval of persisted plan.
3. **Exit** — okf-wiki remember + ingest-or-defer; **path receipt** required to claim complete.

G0–G8 remain as an internal map. Discussion mode has zero implement authority.

## Plan artifact
`artifacts/autogenesis-plans/2026-08-16-discipline-enter-change-exit.md`

## Related
- [[knowledge/vocabulary-lineage-remember-ingest.md]]
- [[knowledge/discipline-enter-change-exit.md]]

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
