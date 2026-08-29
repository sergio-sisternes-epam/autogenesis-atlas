---
type: experience
title: "PINNED: construct FS monitor uses watchdog/inotify, not inotifywait"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Environment has kernel inotify + watchdog. Primary backend watchdog; ctypes fallback; poll last. Never hard-depend on inotifywait CLI."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/challenge-adversarial-construct.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-pin-watchdog-inotify-backend`.

## What happened

Plan: `artifacts/autogenesis-plans/construct-fs-activation-monitor-2026-08-21.md`

- Primary: **watchdog** (inotify on Linux)
- Alt: ctypes `inotify_init`
- Fallback: poll + `backend: poll` in meta
- **Not** required: `inotifywait` CLI

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
