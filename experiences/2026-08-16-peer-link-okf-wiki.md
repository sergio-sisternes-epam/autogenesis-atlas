---
type: experience
title: "peer-link-okf-wiki"
created: 2026-08-16
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: unverified
description: "Migrated experience: peer-link-okf-wiki"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-16-peer-link-okf-wiki`.

## What happened

**Peer skill:** `okf-wiki`  
**Peer store:** `../okf-wiki/references/` (and its `examples/meta-wiki/` process memory)

## What we rely on it for
- okf-wiki is the persistence / memory layer Autogenesis depends on
- Every skill Autogenesis creates or maintains is expected to own an okf-wiki store
- Capture, validate, sources-check, coverage, and experience recording all go through okf-wiki conventions

## Key entry points / contracts
- `scripts/okf_wiki.py` CLI (`capture`, `sources-check`, `validate`, `coverage`, …)
- External-capture-raw-first contract (`resource:` on raw, knowledge cites local `[[raw/…]]`)
- Skill-local store location: `<skill>/references/wiki/`

## Progressive disclosure
- Load okf-wiki SKILL.md when performing capture, validation, or store init
- Load specific modules under okf-wiki/references/ only when the named operation is needed
- meta-wiki (`okf-wiki/references/wiki/`) is process memory for the okf-wiki skill itself; treat as read-only peer context, not as Autogenesis’s primary store

## Notes
Created by learn-skill v0.1.0 during the first formal linking of autogenesis ↔ okf-wiki.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
