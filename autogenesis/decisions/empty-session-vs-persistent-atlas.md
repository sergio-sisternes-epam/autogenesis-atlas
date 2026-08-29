---
type: decision
title: "Empty session vs persistent Atlas store"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "An empty conversation session does not mean the Atlas is empty or should be ignored. Persistence across sessions is required."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: follows
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Decision

“Empty session” means only that no Autogenesis run is currently active in the conversation. The Atlas store under `references/atlas/` is persistent across sessions and must be consulted (via `query`) and written (via `remember` / `work`) as the durable memory.

## Rationale

Carried forward from the former empty-session-vs-persistent-wiki rule, now pointed at the Atlas root. Losing cross-session accumulation would break G8 consolidation and lineage.

## Alternatives considered

- Treat each conversation as a clean slate — rejected (defeats the purpose of a durable substrate).

## Consequences

- Agents must resolve the Atlas root and run `atlas search` / compile checks even on a “fresh” session when the subject is autogenesis or a skill under Autogenesis.
