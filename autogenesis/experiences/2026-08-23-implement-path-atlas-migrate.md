---
type: experience
title: "Implement: path atlas-migrate"
created: 2026-08-23
work_id: autogenesis-path-atlas-migrate-v1
status: done
description: "Approved plan implemented — path module, SKILL registry v0.3.4, workflow-discipline path list."
plan_path: autogenesis/plans/autogenesis-path-atlas-migrate-v1.md
construct_eval: deferred
relates_to:
  - path: autogenesis/work/autogenesis-path-atlas-migrate-v1.md
    kind: implements
  - path: autogenesis/plans/autogenesis-path-atlas-migrate-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
---

## Context

User approved design plan `autogenesis-path-atlas-migrate-v1`. Implement path only (G4 satisfied).

## What happened

1. Created `references/paths/atlas-migrate.md` with full procedure (pins, claim routing, compile gate, discipline rewrite, receipt).
2. Registered path in SKILL.md capabilities table; version **0.3.4**.
3. Added `atlas-migrate` to workflow-discipline activation card path enum.
4. Construct evaluation **deferred** — doc/path-only surface; no runtime scenario suite required for this change-class slice (path module text, not executable behaviour beyond agent procedure).

## Outcome

Path is invocable via Enter card `path: atlas-migrate`. Mechanical core remains atlas CLI.

## Changed files

- references/paths/atlas-migrate.md (new)
- SKILL.md
- references/modules/workflow-discipline.md
- references/atlas/autogenesis/work/autogenesis-path-atlas-migrate-v1.md
- references/atlas/autogenesis/plans/autogenesis-path-atlas-migrate-v1.md
- references/atlas/autogenesis/experiences/2026-08-23-implement-path-atlas-migrate.md

## Follow-ups

- Optional: CLI improve work `atlas-migrate-cli-improve-v1` still draft/designed for later.
- First live use on a non-autogenesis subject will exercise auto-initiate + full claim conversion.
