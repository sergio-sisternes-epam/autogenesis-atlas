---
type: decision
title: "autogenesis implementation status (2026-08-21)"
created: 2026-08-21
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "What autogenesis ships vs pending after 0.2.1 change-class and construct pairing."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Decision

## Implemented

| Capability | Note |
|------------|------|
| Enter / Change / Exit discipline | workflow-discipline module |
| Path modules (design, implement, reevaluate, …) | Activation by path load |
| **change-class** 0.2.1 | hardening \| new-surface \| new-skill |
| Mini-genesis for new-surface | mermaid + interface + cost |
| Construct-aware Exit | scenario version / smokes when relevant |
| Path-load rule | reevaluate claims require path module load |
| Genesis fused | Design quality baseline |
| Subject-wiki lineage via Atlas (formerly okf-wiki) | Exit activation |
| **think-challenge → adversarial construct** 0.3.0 | Design draft + implement Exit suite — [[knowledge/challenge-adversarial-construct]] |

## Pending / thin

| Item | Note |
|------|------|
| Activation card enforcement | Convention; not auto-blocked if omitted |
| Full genesis 8-step on every design | Depth by change-class instead |
| Dream / construct creation ownership refinements | Construct skill owns fixtures; callers use it |
| Cross-repo joint implement | ADR territory |

## Rationale

Migrated from okf-wiki knowledge page `implementation-status-2026-08-21` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
