---
type: decision
title: "Decision: Autogenesis patterns are a thin extension of genesis (B17 only)"
created: 2026-08-22
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Parallel catalogue eliminated. Only B17 ACTIVATION CARD remains. When Autogenesis loads genesis it must inject the extension so B17 is visible. Genesis stays read-only."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
  - path: decisions/decision-patterns-module-v1-capabilities.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

## Locked (updated 2026-08-23)

1. **Location** — Patterns capability remains under **autogenesis** as a thin **extension injector**.
2. **Relationship to genesis** — Genesis Tier-2/3 catalogues are the primary language (read-only). Autogenesis injects only genuine deltas. The sole current delta is **B17. ACTIVATION CARD**.
3. **Injection contract** — When Autogenesis applies the substrate contract to genesis, it **MUST** also load `references/modules/patterns.md` so that B17 is visible for pattern selection and Catalogue Review.
4. **Design-time force** — Catalogue Review (when in scope) now sees genesis catalogues + the injected B17 (and future true extensions). Output includes composition mode (INLINE / LOCAL SIBLING / EXTERNAL / EXTENSION).
5. **No parallel catalogue** — Former Triage Panel and Panel Review have been deprecated. Future panel-style work composes genesis A1 + B1 (and related) directly.
6. **Skip** — Hardening or pure doc changes may mark `catalogue_review: n/a` with one-line rationale.

## Non-goals

- Editing any file inside the genesis skill.
- Re-introducing a parallel Autogenesis catalogue.
- Promoting B17 into the genesis skill itself.

## Related

- [[knowledge/concept-patterns-module]]
- `references/modules/patterns.md` (injector)
- `references/modules/patterns/activation-card.md` (B17)

## Rationale

Migrated from okf-wiki knowledge page `decision-patterns-extend-genesis-catalogue-review` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
