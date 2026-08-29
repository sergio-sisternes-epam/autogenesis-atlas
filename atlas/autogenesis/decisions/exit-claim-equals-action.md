---
type: decision
title: "Exit claim = action"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Prose is not fulfilment. Receipt fields are true only when the Atlas substrate call actually ran."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/lineage-and-remember-via-atlas.md
    kind: related
  - path: autogenesis/decisions/hard-memory-gate.md
    kind: related
  - path: autogenesis/decisions/memory-link-changed-files.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Decision

Prose is not fulfilment.

| Receipt field | Allowed only when |
|---------------|-------------------|
| `remember: yes` | Atlas remember path (or equivalent write) **actually ran** and produced a durable page in the subject Atlas |
| `compile: yes` | `atlas compile --root <atlas>` exited 0 |
| `defer: <reason>` | experience body contains that exact explicit deferral line |

A chat sentence that says “remembered” without the Atlas call + green compile is **not** fulfilment → `incomplete: Exit (G6/G8)`.

## Rationale

Same hard rule as the original exit-claim-equals-action page; substrate names updated from wiki-remember/wiki-ingest to Atlas remember/compile.

## Alternatives considered

- Soft “intent is enough” — rejected (G8 becomes theatre).

## Consequences

Path receipts and Exit checklists reference Atlas only.
