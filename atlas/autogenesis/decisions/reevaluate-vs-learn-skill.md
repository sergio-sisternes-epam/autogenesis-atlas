---
type: decision
title: "reevaluate vs learn-skill"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Migrated knowledge: reevaluate vs learn-skill"
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/reevaluate-handoff-loop.md
    kind: related
  - path: autogenesis/decisions/reevaluate-proposal-template.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Decision

| Path | Role |
|------|------|
| **learn-skill** | Peer-link + usage memory only. No peer mutation. Progressive-disclosure pointers. |
| **reevaluate** | After **material** knowledge change or **explicit** request: classify impact on related skills; write **advisory** handovers into the **subject** wiki; never mutate peers in the same run. |

## Why both

Consolidation without skillset challenge produces stale skill contracts.  
Unbounded reevaluation produces thrashing and cascade noise.

## Hard rules on reevaluate

- Default trigger: **explicit**. Auto only if material delta + cool-down.
- No self-chain from advisory outputs.
- Empty dependency graph is an **explicit** outcome.
- Impact `none` needs rationale; uncertainty recorded; open tasks have owner + domain.
- Recurring gap signature → design-plan candidate + stop for approval.
- Promotion into skill packages still recurrence + human Git PR.

## Proposal quality

reevaluate must emit **structured skill-update proposals** for the subject (always), not only soft advisories. See [[knowledge/reevaluate-proposal-template]].

## Rationale

Migrated from okf-wiki knowledge page `reevaluate-vs-learn-skill` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
