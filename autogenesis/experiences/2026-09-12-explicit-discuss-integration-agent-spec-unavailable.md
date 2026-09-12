---
type: experience
title: "Explicit Discuss integration deferred because agent-spec is unavailable"
created: "2026-09-12"
work_id: "2026-09-12-explicit-discuss-integration"
status: deferred
plan_path: autogenesis/plans/2026-09-12-explicit-discuss-integration.md
construct_eval: "deferred: no package behavior changed"
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-09-12-explicit-discuss-integration.md
    kind: implements
  - path: autogenesis/plans/2026-09-12-explicit-discuss-integration.md
    kind: related
---

## Context

The approved plan requires the agent-spec `specify` path before changing
runtime-facing Autogenesis behavior that removes the embedded Discuss adapter.

## What happened

The current harness exposes no `agent-spec` skill. Its on-demand loader
reported the skill unavailable, so the required specification path cannot be
loaded or invoked. Package source, tests, scenarios, documentation, manifest,
and lockfile were deliberately left unchanged.

## Outcome

deferred: agent-spec must be made available and its `specify` path completed
against work `2026-09-12-explicit-discuss-integration` before implementation
resumes.
