---
type: experience
title: "Autogenesis-aware runtime + governance implemented"
created: 2026-08-16
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Migrated experience: Autogenesis-aware runtime + governance implemented"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-16-aware-runtime-implemented`.

## What happened

Implemented the AwareHook + governance section:

1. Canonical template stored at `autogenesis/references/aware-hook-template.md`
2. Autogenesis skill now requires every generated/upgraded skill to receive the section
3. Back-ported into the four existing focused skills:
   - perf-big-o
   - perf-identify
   - perf-antipattern
   - perf-optimise

Governance (write budget, dedup, pruning, provenance, never-implement) is part of the injected section.
All skills validate cleanly.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
