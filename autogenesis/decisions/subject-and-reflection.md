---
type: decision
title: "Subject skill, okf targeting, and behaviour challenge"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Migrated knowledge: Subject skill, okf targeting, and behaviour challenge"
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Decision

- Every Autogenesis **Run** declares `subject: <skill>` (self or other).
- **Atlas (formerly okf-wiki)** always targets the subject’s canonical wiki root.
- Primary experiences and knowledge for the change live in the **subject** wiki; Autogenesis may keep only a short run pointer when subject ≠ autogenesis.
- Optional **self-reflection → challenge** uses current and recalled subject behaviours; challenge must state **objective** and **motivations**; stored as okf experience with default **might not be used** (no auto-implement).
- Reflection is not plan approval. Core design process remains **genesis**.

## Rationale

Migrated from okf-wiki knowledge page `subject-and-reflection` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
