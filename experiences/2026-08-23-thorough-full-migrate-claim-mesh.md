---
type: experience
title: "Thorough full migrate: every staged file claim-completed with dense relates_to mesh"
created: 2026-08-23
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: done
description: "Re-migrated full wiki (179 files). Converted all 31 knowledge pages to decisions and all 139 raw experiences to experiences. Created 10 historical work hubs. Densified relates_to mesh. Staging left at 0. Compile green."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: records
  - path: decisions/bulk-historical-raw-deferred.md
    kind: supersedes
  - path: experiences/2026-08-23-full-directory-migrate-and-selective-promote.md
    kind: follows
  - path: decisions/corpus-experiences.md
    kind: related
---

## Context

User required extra effort: compile all staged files, leave staging at 0, thoroughly link every page.

## What happened

1. Re-ran `atlas migrate` on the entire former wiki (179 files into staging).
2. Removed staging copies of 10 knowledge pages already claim-complete as decisions.
3. Converted remaining 21 knowledge pages → claim-bearing `decisions/*.md` with Decision/Rationale/Consequences and relates_to.
4. Converted all 139 raw experiences → claim-bearing `experiences/*.md` with Context/What happened/Outcome and thematic relates_to.
5. Created 10 missing historical work hubs so experience `implements` edges resolve.
6. Densified relates_to mesh: every decision links to migration work + memory substrate + discipline core + thematic cluster peers.
7. Rebuilt decisions/, experiences/, work/, and root indexes.
8. Cleared staging completely.

## Outcome

- decisions: 32
- experiences: 144 (incl. this page)
- work hubs: 11
- staging: 0
- `atlas compile` exit 0

Prior selective-only and bulk-deferral stances are superseded by this complete claim migration. The old `references/wiki/` remains as optional read-only provenance archive.

## Follow-ups

None required for staging emptiness. Future live-migration BM25 work can index this Atlas directly.
