---
type: decision
title: "Hard memory gate (Atlas)"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Memory ops at Exit must go through Atlas paths; no hand-written lineage substitutes."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: follows
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/lineage-and-remember-via-atlas.md
    kind: related
  - path: autogenesis/decisions/exit-claim-equals-action.md
    kind: related
  - path: autogenesis/decisions/memory-link-changed-files.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Decision

At Exit, memory operations **must** load and follow Atlas path modules (`remember` / `query` / `work`). Inventing “lineage” text or writing pages outside the Atlas root without compile is a hard failure.

## Rationale

Prevents the dual-home and hand-craft failure modes that the original hard-memory-gate page existed to stop; now pointed at Atlas.

## Alternatives considered

- Allow parallel write to old wiki — rejected.

## Consequences

Agents activate the **atlas** skill (substrate contract) for memory, never invent store layout.
