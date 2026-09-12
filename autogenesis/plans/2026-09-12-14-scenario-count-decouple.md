---
type: protostar
title: Decouple source-contract from exact scenario count
created: 2026-09-12
work_id: 2026-09-12-14-solid-dogfood-autogenesis
status: open
kva: forming
growth: true
star_kind: probe
origin: derived
sensitivity: internal
description: Park stopping the source-contract inventory from asserting an exact scenario count unless that count is an intentional governance gate.
relates_to:
  - path: autogenesis/plans/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: derived_from
  - path: autogenesis/work/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: implements
---

## Pending

`scripts/test_source_contract.py` currently couples to an exact scenario
inventory size. Treat that coupling as low-priority hardening unless the count
is deliberately governed. Coordinate with any parallel source-contract PR.

## Origin

Low-ranked SOLID follow-up from 2026-09-12; keep isolated from issue 9.
