---
type: experience
title: "2026-08-16 Remember: autogenesis memory uses okf-wiki on subject store"
created: 2026-08-16
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Link hard memory gate to okf-wiki remember/experience intent; do not treat direct writes as complete."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-16-remember-okf-wiki-required-for-memory`.

## What happened

Autogenesis Run **hard memory gate** (subject wiki validate + lineage + ingest or deferral) must be executed via **okf-wiki** against the **subject** skill’s `references/wiki/`.

Related subject experience: apm store `raw/experiences/2026-08-16-remember-okf-wiki-for-memory.md`.

When subject ≠ autogenesis, autogenesis wiki holds only a short pointer; full remember lives in the subject store.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
