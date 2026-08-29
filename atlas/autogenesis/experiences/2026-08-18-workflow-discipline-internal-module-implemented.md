---
type: experience
title: "Implemented workflow-discipline internal module"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Extracted the Enter|Change|Exit workflow engine into references/modules/workflow-discipline.md; thinned root SKILL.md; updated design path and knowledge page; instituted integrated Genesis+Autogenesis plan rule."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-workflow-discipline-internal-module-implemented`.

## What happened

## What the user asked
- Liked the structured workflow (cards, gates, approvals).
- Wanted a module that replicates the discipline.
- Decided it should be an **internal module** inside autogenesis (not a peer skill), extractable later.
- Required that every Autogenesis design plan embed the full Genesis diagrams and artifacts (integrated discipline).
- Approved the plan and said “proceed”.

## What we did (implement path)

1. Created `references/modules/workflow-discipline.md` as the single source of truth for:
   - Activation card schema
   - Enter | Change | Exit clusters
   - Gate map G0–G8
   - Discussion/run rules (including hard block on discussion → implement)
   - Path receipt
   - Substrate-contract reminder
   - Future extraction notes

2. Thinned root `SKILL.md`: replaced the large inline discipline sections with a load instruction pointing to the new module.

3. Updated `references/paths/design.md` to require that every design plan embed the full Genesis artifacts (intent, component diagram, sequence diagram, composition decision).

4. Updated knowledge page `references/wiki/knowledge/discipline-enter-change-exit.md` to cite the new module as source of truth and mention the integrated-plan rule.

## Pinned decisions applied
- P1–P6 from the approved plan (internal module, name, thin root, extraction notes, no domain path changes, always embed Genesis diagrams).

## Version identity
- Module version field: `2026-08-18`
- Plan ID: `2026-08-18-workflow-discipline-internal-module`

## Changed files

- `references/modules/workflow-discipline.md` (created)
- `SKILL.md` (thinned)
- `references/paths/design.md` (integrated-plan rule added)
- `references/wiki/knowledge/discipline-enter-change-exit.md` (updated to cite module)

## Related
- [[knowledge/discipline-enter-change-exit]]
- [[knowledge/core-process]]
- [[knowledge/path-modules-and-gates]]
- Plan: `artifacts/autogenesis-plans/2026-08-18-workflow-discipline-internal-module.md`

## Ingest deferral
Knowledge page was materially updated. Full `wiki-ingest` is deferred to a follow-up housekeeping run (reason: keep this implement focused on the approved scope; ingest can be run cleanly after structural gates).

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
