---
type: decision
title: "Active pending backlog (design + implement)"
created: 2026-08-21
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Open work keyed by work_id for navigable correlation with plans and implement experiences."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

Rows keyed by **work_id** (alias in parentheses).

| work_id | Alias | Item | Owner |
|---------|-------|------|-------|
| construct-e2e-scenario-v4 | C-P1 | Scenario v4 E2E activation+discipline smokes | construct |
| construct-write-op-events | C-P2 | FS write / write-blocked events | construct |
| construct-modules-convention | C-P3 | Retire allowlist → references/modules/ | construct |
| construct-symlink-smoke | C-P4 | Dual-path open smoke | construct |
| construct-archive-evidence | C-P5 | Archive evidence helper | construct |
| autogenesis-adversarial-exit-latest | A-P-ADV-1 | Exit: run latest adversarial vN; keep prior | autogenesis |
| autogenesis-adversarial-checker | A-P-ADV-2 | Shared check_adversarial_gate.py | autogenesis |
| autogenesis-adversarial-receipt | A-P-ADV-3 | Receipt field adversarial_scenarios | autogenesis |
| autogenesis-adversarial-suite-review | A-P-ADV-4 | P12 suite-size review on next behaviour-change | autogenesis |
| autogenesis-activation-card-enforce | A-P1 | Hard enforce activation card | autogenesis |
| autogenesis-path-fs-align | A-P3 | path_modules_loaded ↔ FS log | autogenesis |
| agent-brain-dream-path | B-P1 | dream path | agent-brain |
| agent-brain-think-forget-decide | B-P2 | think / forget / decide | agent-brain |
| agent-brain-adr-001-conflict-loops | B-P3 | ADR-001 | agent-brain |
| agent-brain-adr-002-cross-repo | B-P4 | ADR-002 | agent-brain |
| agent-brain-unresolved-task-ux | B-P5 | Unresolved-task list UX | agent-brain |
| agent-brain-e2e-docker-train | B-P7 | E2E docker train under v4 contract | agent-brain |

## Closed (navigable)

| work_id | Status |
|---------|--------|
| autogenesis-work-id-lineage | **done** — [[raw/experiences/work-autogenesis-work-id-lineage]] |
| autogenesis-construct-boundary | done (0.2.2 boundary R1–R5) |
| autogenesis-challenge-adversarial-construct | **done** (0.3.0) — [[raw/experiences/work-autogenesis-challenge-adversarial-construct]] |

## Rationale

Migrated from okf-wiki knowledge page `pending-backlog-active` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
