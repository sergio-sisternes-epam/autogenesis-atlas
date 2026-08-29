---
type: experience
title: "SCHEMA expanded: Autogenesis space plans/ with type plan"
created: 2026-08-23
work_id: autogenesis-plan-home-subject-atlas-v1
status: done
description: "Replaced experience-as-plan convention with dedicated plans/ folder, type plan, template, and autogenesis_space in SCHEMA."
relates_to:
  - path: autogenesis/work/autogenesis-plan-home-subject-atlas-v1.md
    kind: implements
  - path: autogenesis/decisions/plan-home-is-subject-atlas.md
    kind: records
---

## Context

User asked: rather than experience, expand SCHEMA and store plans in autogenesis/plans inside the target atlas — create an Autogenesis space.

## What happened

- SCHEMA.json → 1.1 with `plan` type, template contract, `autogenesis_space`, recommended_folders including plans
- templates/plan.md added
- plans/index.md Autogenesis space index
- SKILL + workflow-discipline + design/initialise/reevaluate point at `plans/<work_id>.md` type plan
- Decision plan-home updated

## Outcome

Plan home is a first-class Atlas space, not an experience naming hack.

## Follow-ups

When initiating Atlas for other subjects under Autogenesis, copy autogenesis_space + plan template into the new root.
