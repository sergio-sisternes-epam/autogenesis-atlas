---
type: protostar
title: "Require a valid plan status key"
created: "2026-10-12"
work_id: "2026-10-12-catalogue-description-hardening"
status: open
kva: forming
growth: true
star_kind: action
origin: derived
sensitivity: internal
description: "Park a body sentence that a persisted plan must carry a valid workflow-discipline status. Not implement authority."
relates_to:
  - path: autogenesis/plans/2026-10-12-catalogue-description-hardening.md
    kind: derived_from
  - path: autogenesis/work/2026-10-12-catalogue-description-hardening.md
    kind: implements
---

## Pending

Owner run `20261011T214247Z-autogenesis-a4038b5` had a plan with no status
key and one at `awaiting-approval`, which is a receipt disposition, not a
plan status. A root or design sentence should require a value from
`proposed | designed | approved | implementing | done | deferred | waived`.

Not folded into the catalogue-description plan. That sentence lives in the
body, so it cannot reach a Run that never activated Autogenesis. It needs
its own design before any edit.

## Origin

Separate follow-up F1 of `2026-10-12-catalogue-description-hardening`.
