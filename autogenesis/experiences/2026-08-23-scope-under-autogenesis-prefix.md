---
type: experience
title: "Scope all Autogenesis-authored Atlas content under autogenesis/"
created: 2026-08-23
work_id: autogenesis-plan-home-subject-atlas-v1
status: done
description: "Moved experiences, decisions, work, plans under autogenesis/; SCHEMA 1.2; 191 path rewrites; layout ready for other target skills."
relates_to:
  - path: autogenesis/work/autogenesis-plan-home-subject-atlas-v1.md
    kind: implements
  - path: autogenesis/decisions/plan-home-is-subject-atlas.md
    kind: records
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
---

## Context

User required Autogenesis Atlas content scoped under `autogenesis/` so future target-skill Atlases stay organised (subject-native root vs Autogenesis-authored namespace).

## What happened

1. Moved experiences/, decisions/, work/, plans/ → `autogenesis/`.
2. Rewrote relates_to paths (191 files).
3. SCHEMA 1.2: `autogenesis_space.root = autogenesis`, plan path `autogenesis/plans/<work_id>.md`.
4. Updated SKILL, workflow-discipline, design/initialise/reevaluate.
5. Templates remain at Atlas root (not under autogenesis/) so they are not treated as concept pages.

## Outcome

Compile green. Layout is the template for any subject Atlas Autogenesis touches.

## Follow-ups

Initiate-Atlas on other skills must create the full `autogenesis/` tree per SCHEMA `initiate_includes`.
