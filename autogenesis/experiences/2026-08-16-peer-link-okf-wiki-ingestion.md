---
type: experience
title: "peer-link-okf-wiki-ingestion"
created: 2026-08-16
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: unverified
description: "Migrated experience: peer-link-okf-wiki-ingestion"
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-16-peer-link-okf-wiki-ingestion`.

## What happened

**Peer:** `okf-wiki`  
**Peer store:** `../okf-wiki/references/wiki/`

## What we rely on for ingestion
- `wiki-remember` / raw experience filing conventions
- `wiki-ingest` (and propose/extract patterns) to promote durable knowledge
- CLI: `validate`, `coverage`, `sources-check`, `index-check`, `capture`
- External-capture-raw-first contract

## Progressive disclosure
- Load okf-wiki SKILL.md + `references/modules/wiki-remember.md` when filing experiences
- Load `references/modules/wiki-ingest.md` when promoting knowledge
- Load CLI help for structural gates after writes

## Contract
Autogenesis must not reimplement ingestion. Dead knowledge is a discipline failure when durable conclusions stay raw-only without explicit deferral.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
