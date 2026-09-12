---
type: work
title: Remove Construct from the Autogenesis runtime contract
created: 2026-09-11
work_id: 2026-09-11-remove-construct-binding
status: done
description: Remove the unavailable private evaluator from live Autogenesis contracts while preserving portable scenarios and historical evidence.
relates_to:
  - path: autogenesis/plans/2026-09-11-remove-construct-binding.md
    kind: related
  - path: autogenesis/work/2026-09-11-instruction-first-skill-modules.md
    kind: follows
  - path: autogenesis/experiences/2026-09-11-evaluator-decoupling-implementation.md
    kind: related
---

# Remove Construct from the Autogenesis runtime contract

## Scope

Remove Construct-specific live routing, gates, fields and current-scenario
expectations. Keep native scenarios, direct deterministic checks, evidence,
GitHub CI and immutable historical records.

## Status

The user established the direction at 2026-09-11T18:24:45+01:00 and then
explicitly approved the persisted new-surface plan. Implementation is locally
complete: live instructions are evaluator-neutral, v4 is current, v3 is
historical, and repository/deployment checks pass. GitHub CI remains the final
release gate rather than part of this local work closure.

## Outcomes

- [Design and implementation handoff](../plans/2026-09-11-remove-construct-binding.md)
- [Implementation evidence and preservation boundary](../experiences/2026-09-11-evaluator-decoupling-implementation.md)
