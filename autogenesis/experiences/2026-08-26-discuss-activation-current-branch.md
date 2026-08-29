---
type: experience
title: "Subject-root record of current discuss branch"
created: "2026-08-26"
work_id: "2026-08-26-autogenesis-discuss-activation"
status: probed
description: "Applies caller atlas_root: this page lives on the subject Atlas and names the live discuss branch."
tags: [discuss, probe, current-branch]
origin: derived
sensitivity: internal
stage: discussion
artifact: autogenesis/plans/2026-08-26-autogenesis-discuss-activation.md
atlas_root_intended: subject
external_ref: "atlas:discuss-skill-memory:wire/probe-connections.md"
relates_to:
  - path: autogenesis/work/2026-08-26-autogenesis-discuss-activation.md
    kind: implements
  - path: autogenesis/plans/2026-08-26-autogenesis-discuss-activation.md
    kind: related
  - path: autogenesis/experiences/2026-08-26-discuss-activation-session.md
    kind: follows
---

## Context

Enhancement 12: Autogenesis must pass subject `atlas_root` into discuss. This session's fabric was already on discuss Atlas. This page is the subject-root stand-in for the current branch so the test cluster has a write-home node.

## What happened

Canonical work and plan live in this Atlas. Live Q-nodes remain on discuss Atlas (not dual-written). This node points at `wire/probe-connections.md` via `external_ref`.

## Outcome

Subject store now holds work (canonical) + plan + session + current-branch record, all with `stage` and `artifact`.
