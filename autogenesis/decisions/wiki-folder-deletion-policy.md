---
type: decision
title: "Wiki folder deletion policy (post atlas-migrate)"
created: 2026-08-24
work_id: post-migrate-cleanup-v1
status: active
description: "Legacy references/wiki/ is read-only archive after successful atlas-migrate. No auto-delete on migrate Exit. Deletion is human-gated, requires Atlas green + migrate lineage, and must be recorded as an experience."
tags: [policy, wiki, archive, atlas-migrate]
relates_to:
  - path: autogenesis/work/post-migrate-cleanup-v1.md
    kind: implements
  - path: autogenesis/decisions/atlas-migrate-must-require-quality-relates-to.md
    kind: related
---

## Decision

1. **Do not auto-delete** — `atlas-migrate` never deletes `references/wiki/` on Exit.
2. **Archive, not authority** — after successful migrate (compile green + discipline rewrite), wiki is read-only archive only; new process memory goes to Atlas.
3. **Human-gated delete** — deletion is an explicit user action, never implied by migrate.
4. **Preconditions** — Atlas present + compile green; migrate experience exists; no open work treating wiki as live source.
5. **Record the delete** — experience on skill Atlas listing removed paths; optional log.md append.
6. **Project-level wiki** (medium/gamma workspaces) — same rules; migrate-project source then archive or human-gated delete.
7. **Excluded** — skills that did not complete atlas-migrate (e.g. okf-wiki, knowledge-crawl, terraform) keep their stores.

## First application

2026-08-24: user approved policy and requested delete of all successfully migrated subject `references/wiki/` folders in the same session.
