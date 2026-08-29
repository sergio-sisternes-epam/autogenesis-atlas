---
type: decision
title: "Patterns module (Autogenesis extension injector)"
created: 2026-08-22
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Thin extension injector. When Autogenesis loads genesis, this module is also loaded so B17 ACTIVATION CARD is visible. No parallel catalogue. Former Triage Panel and Panel Review deprecated."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
  - path: autogenesis/decisions/decision-patterns-module-v1-capabilities.md
    kind: related
  - path: autogenesis/decisions/decision-patterns-extend-genesis-catalogue-review.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Decision

## What it is (after 2026-08-23)

A thin **extension injector** at `references/modules/patterns.md`.  

When Autogenesis applies the substrate contract to the skill named `genesis`, this module **MUST** also be loaded so that **B17. ACTIVATION CARD** (and any future true deltas) are visible alongside the genesis Tier-2 / Tier-3 catalogues.

- Genesis remains read-only.
- No parallel Autogenesis pattern catalogue is maintained.
- Former entries Triage Panel and Panel Review have been moved to `patterns/deprecated/`.

## Sole remaining pattern

**B17. ACTIVATION CARD** (Behavioral / Control & Safety)  
File: `patterns/activation-card.md`  
Classical analog: Process Entry Gate + Receipt.

## Admission bar (for any future extension)

Proven use first. Single observation → draft only. Create to active requires repeated-use evidence.

## How to use

1. Load genesis as usual.
2. Load this module (mandatory injection).
3. B17 is then available for pattern selection and Catalogue Review.

## Related

- [[knowledge/decision-patterns-extend-genesis-catalogue-review]]
- `references/modules/workflow-discipline.md` (source of process detail for B17)
- Upstream: genesis `assets/design-patterns.md` and `assets/architectural-patterns.md`

## Rationale

Migrated from okf-wiki knowledge page `concept-patterns-module` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
