---
type: decision
title: "Discipline: Enter | Change | Exit"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Public blocking clusters for Autogenesis. Exit lineage now activates Atlas, not okf-wiki."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: follows
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/core-process.md
    kind: related
  - path: autogenesis/decisions/path-modules-and-gates.md
    kind: related
  - path: autogenesis/decisions/progressive-disclosure-paths.md
    kind: related
  - path: autogenesis/decisions/block-discussion-to-implement.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Decision

The public blocking clusters remain **Enter → Change → Exit**. Source of truth is still `references/modules/workflow-discipline.md`.

- **Enter:** activation card (`mode`, `subject`, `path`, `path_module`, `intent`). Discussion = no implement authority.
- **Change:** design (genesis → challenge → pin → C1–C5 → stop for approval); implement only after explicit approval of a persisted plan.
- **Exit:** lineage activates **Atlas** on the subject Atlas root (`remember` / `work` + green compile), not okf-wiki.

## Rationale

Carried forward from the original Enter|Change|Exit design; substrate updated to Atlas so the discipline matches the memory authority decision.

## Alternatives considered

- Keep Exit on okf-wiki — rejected (contradicts memory-substrate-is-atlas).

## Consequences

workflow-discipline.md and path modules must load Atlas paths at Exit. Path receipts use `atlas_root` and `compile`.
