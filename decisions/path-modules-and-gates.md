---
type: decision
title: "Path modules and gates"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Path modules under references/paths/ are the only execution surface; G0–G8 map into Enter|Change|Exit."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/core-process.md
    kind: related
  - path: decisions/progressive-disclosure-paths.md
    kind: related
  - path: decisions/block-discussion-to-implement.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

Path modules under `references/paths/` are **not** catalog skills. The agent must `read_file` the named path module before executing it. Gates G0–G8 remain mapped into Enter|Change|Exit; G2/G6/G8 now require Atlas root + green compile.

## Rationale

Unchanged progressive-disclosure rule; only the memory substrate behind the gates changed.

## Alternatives considered

- Treat path modules as peer root skills — rejected (catalog explosion).

## Consequences

Registry stubs stay thin; full procedure lives only in the path file.
