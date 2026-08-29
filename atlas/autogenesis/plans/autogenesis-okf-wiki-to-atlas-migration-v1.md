---
type: plan
title: "Design plan (hardening): Autogenesis memory substrate → Atlas only"
created: 2026-08-23
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: done
change_class: hardening
subject: autogenesis
description: "Moved from artifacts/autogenesis-plans/ into Autogenesis space plans/."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/plan-home-is-subject-atlas.md
    kind: related
---

## Intent + scope

# Design plan (hardening): Autogenesis memory substrate → Atlas only

**work_id:** autogenesis-okf-wiki-to-atlas-migration-v1  
**change-class:** hardening  
**status:** approved-by-user-direction (explicit “ensure only atlas is used”)

## Intent + scope

Replace every remaining hard-coded dependency on the okf-wiki skill / `references/wiki/` as the write/query authority for Autogenesis process memory with the Atlas skill and `references/atlas/`.

## Acceptance

- SKILL.md Experience source + progressive disclosure + failure modes name only Atlas.
- workflow-discipline.md hard boundaries and session language name only Atlas.
- At least the Exit claims of the most frequently used path modules (design, implement, reevaluate, research) no longer require okf-wiki activation.
- New Atlas root remains compile-green.
- Old `references/wiki/` left as read-only historical archive (no delete).

## Non-goals

- Bulk rewrite of 139 raw experiences.
- Changing other skills’ wikis.
- Full BM25 / live migration (separate work).

## Genesis Artifacts (abbreviated — hardening)

- Intent + scope + acceptance above.
- No new surface; text-only contract change.

## Genesis Artifacts

See Intent + scope (hardening abbreviated artifacts in original plan body).

## Acceptance

Discipline uses Atlas only; migration work closed; compile green.

## Stop for approval

Already approved by user direction and implemented.
