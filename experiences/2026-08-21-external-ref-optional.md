---
type: experience
title: "Enhancement: optional external_ref on work_id lineage"
created: 2026-08-21
work_id: autogenesis-work-id-lineage
status: raw
description: "Optional opaque external_ref for GitHub/Jira/etc. No client; correlation only."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: work/autogenesis-work-id-lineage.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-external-ref-optional`.

## What happened

Optional field on plan, work node, implement experience. Agnostic string (URL or key). Not used yet; reserved for future host trackers.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
