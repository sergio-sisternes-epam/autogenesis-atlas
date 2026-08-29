---
type: decision
title: "reevaluate handoff loop"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Migrated knowledge: reevaluate handoff loop"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/reevaluate-handoff-loop.md
    kind: related
  - path: decisions/reevaluate-proposal-template.md
    kind: related
  - path: decisions/reevaluate-vs-learn-skill.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

## Path role
`reevaluate` is the **transfer signal** after material knowledge change: structured skill-update proposals, then (when evolution-worthy) a **challenged design plan** and target-skill todo for **user judgment**.

## Pipeline
1. Structured proposals (mandatory subject template).
2. If evolution-worthy (capability-gap / correctness / safety or non-trivial surface change):
   - Draft design plan in the subject Atlas.
   - Automatic challenge ×1 (`confidence: limited`).
   - Target skill experience + todo (`gate: user-judgment`, signature dedupe).
3. Caller (agent-brain Learn) emits user **decision packet**.
4. No package mutation until user judges.

## Related
- [[knowledge/reevaluate-vs-learn-skill]]
- [[knowledge/reevaluate-proposal-template]]
- [[knowledge/train-learn-skill-evolution-loop]]

## Rationale

Migrated from okf-wiki knowledge page `reevaluate-handoff-loop` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
