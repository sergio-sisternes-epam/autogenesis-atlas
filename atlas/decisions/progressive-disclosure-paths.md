---
type: decision
title: "Progressive disclosure of path modules"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Load one path module at a time; never load every path or invent procedure from memory."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/path-modules-and-gates.md
    kind: related
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/core-process.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/block-discussion-to-implement.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

Working pattern: activate root skill → read SKILL.md → select path → **read_file the path_module** → execute. If Exit needs memory, activate **atlas** and load the named Atlas path module. Do not load every path module at once or invent lineage.

## Rationale

Same progressive-disclosure contract; memory step now points at Atlas.

## Alternatives considered

- Eager-load all paths — rejected (token and confusion cost).

## Consequences

Failure modes list “skipping Atlas” instead of “skipping okf-wiki”.
