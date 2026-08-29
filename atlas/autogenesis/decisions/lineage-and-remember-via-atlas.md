---
type: decision
title: "Lineage, G6/G8 and remember/ingest now use Atlas paths"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Vocabulary and gates that previously required wiki-remember / wiki-ingest-or-defer now require Atlas remember / query / work. Supersedes the okf-wiki-centric lineage page."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: follows
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/hard-memory-gate.md
    kind: related
  - path: autogenesis/decisions/exit-claim-equals-action.md
    kind: related
  - path: autogenesis/decisions/memory-link-changed-files.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Decision

Lineage (G6), Exit consolidation (G8) and all “remember / ingest” operations under Autogenesis load and follow **Atlas** path modules:

- `atlas/paths/remember.md` for writing experiences, decisions, lessons, recipes
- `atlas/paths/query.md` for retrieval
- `atlas/paths/work.md` for work_id hubs

The old names `wiki-remember`, `wiki-ingest-or-defer` and the requirement to activate the okf-wiki skill are retired for this skill.

## Rationale

Consistent with the substrate decision. Path modules already encode the agent behaviour; inventing parallel “lineage” text that still points at okf-wiki would recreate the dual-home problem.

## Alternatives considered

- Keep the old vocabulary strings and only change the target store — rejected (confusing, breaks progressive disclosure).
- Delay vocabulary update until full bulk migration — rejected (discipline must be consistent immediately).

## Consequences

- workflow-discipline.md and every path module that mentioned okf-wiki memory ops must be edited.
- Path receipts and Exit claims reference Atlas roots and compile status.
- Historical raw experiences that used the old vocabulary remain valid lineage sources but are not the write path.
