---
type: decision
title: "Internal think modules"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Migrated knowledge: Internal think modules"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

Autogenesis owns progressive-disclosure copies of the three think skills under `references/modules/`:

| Module | Purpose |
|--------|---------|
| `think-challenge.md` | Grounded adversarial counters (used by design path + on-request) |
| `think-grill.md` | Socratic questioning (on-request) |
| `think-ramble.md` | Free-form capture → subject Atlas (on-request) |

**Rules**
- Load with `read_file` on the module path. Never by root skill name.
- While an Autogenesis Run is active, the three think verbs resolve to these modules (see root SKILL.md “Internal think modules” section).
- Root-level `think-*` skills remain untouched and available for non-Autogenesis use.
- Modules may diverge from the root snapshots over time; evolution happens only through Autogenesis design → approve → implement on subject=autogenesis.
- Memory ops inside the modules always go through the multi-harness substrate contract to `Atlas (formerly okf-wiki)` / `okf` on the **subject** wiki.

This is the first use of a `references/modules/` layer inside autogenesis (paths remain under `references/paths/`).

## Rationale

Migrated from okf-wiki knowledge page `internal-think-modules` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
