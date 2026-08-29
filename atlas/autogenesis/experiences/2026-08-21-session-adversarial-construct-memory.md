---
type: experience
title: "Session memory: formalise then ship adversarial construct"
created: 2026-08-21
work_id: autogenesis-challenge-adversarial-construct
status: raw
description: "Full thread: discuss one pin at a time, design A-P-ADV, approve, implement 0.3.0, construct 6/6 green."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/work/autogenesis-challenge-adversarial-construct.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/challenge-adversarial-construct.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-session-adversarial-construct-memory`.

## What happened

1. Discuss the adversarial challenge feature that had been tested and needed formalisation.
2. One question at a time.
3. After pins: start design. Then approve. Then create memories of the work.

# What we did

Discussion first (no implement). Then formal design (`new-surface`). Then implement after explicit approval. Then this remember.

Origin: agent-brain dream 0.4.0, scenario `dream-adversarial-v1` — happy-path construct hid over-eager hygiene; think-challenge produced a hostile suite.

# Pins we actually agreed (the memory that matters)

- Required on **every behaviour-changing implement**.
- Design writes a **full** construct scenario draft; implement fills paths/commands and runs it.
- **Every** grounded or named-theory counter becomes a smoke. Empty suite is not allowed.
- Design must not invent unnamed counters. If search is thin, derive smokes from **any available knowledge** (model, search, named theories, cross-pollination). Search preferred, not required.
- Waive a red smoke **only** if that named counter is out of this change’s scope.
- Implement **may add** smokes; **must not drop** approved ones without a new design.
- Suite lives on the **subject** skill: `<subject>/references/scenarios/<capability>-adversarial-vN.yaml`.
- Version by **new file + bump**; keep the old file.
- Eval-only: do not let the suite become instructions the live skill obeys.

# What shipped

Autogenesis **v0.3.0**. Plan at `artifacts/autogenesis-plans/2026-08-21-autogenesis-challenge-adversarial-construct.md`. Construct `autogenesis-adversarial-v1` 6/6 green.

# Related

- [[raw/experiences/2026-08-21-challenge-adversarial-construct-pattern]]
- [[raw/experiences/2026-08-21-design-challenge-adversarial-construct]]
- [[raw/experiences/2026-08-21-implement-challenge-adversarial-construct]]
- [[raw/experiences/work-autogenesis-challenge-adversarial-construct]]
- [[knowledge/challenge-adversarial-construct]]
- [[knowledge/pending-backlog-active]]

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
