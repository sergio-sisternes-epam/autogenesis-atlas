---
type: decision
title: "Decision: patterns module v1 capabilities (kept vs deferred)"
created: 2026-08-22
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Pinned after think-challenge: Identify, Extract (gated), Create (repeated-use), Record known-use, Load, List/query for v1. Scan/detect and Relate deferred."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
  - path: decisions/decision-patterns-extend-genesis-catalogue-review.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

Pinned from the discussion on a progressive patterns module under autogenesis (location B, proven-use-first admission, template v1, active capability scope C), after think-challenge.

## Kept for version 1

| Capability | Constraint |
|------------|------------|
| **Identify** | Flags candidates only; does not create |
| **Extract** | Produces draft only; admission still requires proven repeated use |
| **Create** | Requires evidence of *repeated* use before a pattern file is written |
| **Record known-use** | Must be cheap; ideally tied to existing remember/Exit; living section on each pattern |
| **Load** | Progressive, by id or category — never dump the whole catalogue |
| **List/query** | Same progressive rule |

## Deferred (do not implement in v1)

| Capability | Why deferred |
|------------|----------------|
| **Scan/detect** | High risk of false candidates and undermining proven-use-first; extraction/mining literature shows low precision and evaluation difficulty |
| **Relate** | Useful later for a pattern language graph; not needed while the catalogue has one (or few) patterns |

## Supporting locks (discussion)

1. **Location** — Progressive module under autogenesis  
2. **Admission bar** — Proven use first (generalise only from repeated, working solutions)  
3. **Template** — Candidate template as v1; Known uses is a living record of Autogenesis applications  
4. **Scope** — Active capability (not docs-only)

## Residual risks (from think-challenge)

- Extract/Scan can flood weak candidates if not gated  
- Living Known uses is valuable but maintenance-heavy — keep Record cheap  
- Feature surface can become a Blob — v1 stays minimal  
- Load/List must stay progressive as the catalogue grows  
- Create must not allow single-observation “patterns”

When a second and third proven pattern exist and design Runs feel the need, revisit Scan/detect and Relate via a new design path.

## Rationale

Migrated from okf-wiki knowledge page `decision-patterns-module-v1-capabilities` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
