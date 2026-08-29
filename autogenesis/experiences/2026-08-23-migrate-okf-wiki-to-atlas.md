---
type: experience
title: "Bootstrap Atlas root and migrate key memory discipline pages from okf-wiki"
created: 2026-08-23
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: done
description: "Created references/atlas/ under autogenesis, migrated three authoritative knowledge pages as decisions, left bulk raw experiences deferred."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: records
---

## Context

User requested: atlas skill migrate autogenesis skill from okf-wiki skill to atlas skill; afterwards autogenesis reviews discipline so only Atlas is used.

## What happened

1. Opened work hub in atlas skill store + local mirror.
2. Bootstrapped full Atlas root (SCHEMA, templates, indexes, log) under autogenesis/references/atlas/.
3. Migrated + promoted three critical pages:
   - memory-via-okf-wiki → decisions/memory-substrate-is-atlas.md (accepted)
   - vocabulary-lineage-remember-ingest → decisions/lineage-and-remember-via-atlas.md (accepted)
   - empty-session-vs-persistent-wiki → decisions/empty-session-vs-persistent-atlas.md (accepted)
4. Bulk historical raw/ (139 experiences) left in place as read-only archive; full rewrite deferred to atlas-bm25-and-live-migration-v1 style work.

## Outcome

New Atlas root exists. Key authority pages now live under Atlas and supersede the old okf-wiki rules. Staging empty. Ready for compile + hand-off to autogenesis discipline review.

## Related

See frontmatter relates_to.

## Follow-ups

- Compile green.
- Autogenesis skill path review-package / reevaluate to rewrite SKILL.md + modules so only Atlas is referenced.
