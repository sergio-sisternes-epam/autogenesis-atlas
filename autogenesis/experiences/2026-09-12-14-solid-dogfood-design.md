---
type: experience
title: Designing Autogenesis SOLID dogfood work
created: 2026-09-12
work_id: 2026-09-12-14-solid-dogfood-autogenesis
status: complete
subject: autogenesis
origin: derived
sensitivity: internal
description: Autogenesis design operation opened GitHub-linked work, a new-surface plan, and four protostars. Catalog skill was v0.4.3 so workspace v0.5.0 was the router. Stops for approval.
relates_to:
  - path: autogenesis/work/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: implements
  - path: autogenesis/plans/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: records
  - path: autogenesis/experiences/2026-09-12-14-solid-improvement-recommendations.md
    kind: follows
  - path: autogenesis/experiences/2026-09-12-solid-skill-design-lens-implementation.md
    kind: derived_from
---

# Designing Autogenesis SOLID dogfood work

## Context

The user invoked Autogenesis to build work and protostars, linked to a GitHub
issue, applying SOLID to Autogenesis before a new version. Dogfooding was
named as important. They also asked to persist memories of the implementation
and the later analysis/recommendation discussion.

## What happened

Workspace Autogenesis v0.5.0 was used as the parent router because the catalog
copy is v0.4.3 and lacks the lens. Atlas was already mounted on the lens store
branch at `161fb87c0420f149cd1efba9e998eab575bce13a`; this design used a new
dedicated Atlas branch from that commit so the lens pull request gitlink stays
untouched. Change-class is new-surface. Genesis, think-challenge, and patterns
(B17 active, S8 not-selected) were applied. No product files were edited.

## Outcome

Plan, work hub, four protostars, and linking experiences are persisted and
await explicit approval. Implement remains blocked.
