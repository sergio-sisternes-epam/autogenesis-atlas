---
type: experience
title: "PENDING inventory \u2014 designs and implementations (2026-08-21 evening)"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Single snapshot of work still open after boundary 0.2.2, construct 0.2.1 classifier, FS monitor, mesh, train/learn. For resume and prioritisation."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/challenge-adversarial-construct.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-pending-design-and-implement-inventory`.

## What happened

## Shipped recently (do not re-open as pending)

| Item | Version / note |
|------|----------------|
| autogenesis change-class + construct Exit + path-load | 0.2.1 |
| autogenesis↔construct boundary R1–R5 + post-implement gate | **0.2.2** |
| construct FS monitor (watchdog) | 0.2.0 |
| construct classifier module allowlist + in_construct_workspace | **0.2.1** |
| construct boundary docs | **0.2.2** |
| okf-wiki mesh resolve/dependents/project-root | 0.4.x |
| agent-brain train/learn vocabulary, overlay, reevaluate handoff | 0.3.3 |
| Activation vs discipline pin | pinned |

## Pending — construct

| ID | Item | Class | Notes |
|----|------|-------|-------|
| C-P1 | Scenario **v4** E2E smokes (A1–A9 activation matrix + D floors) | hardening | Designed in HANDOVER-E2E; YAML still v3 |
| C-P2 | `op: write` / write-blocked events | new-surface | F3 deferred |
| C-P3 | Retire process allowlist → migrate docs to `references/modules/` | hardening | Counter 1 long-term |
| C-P4 | Dual-path open smoke (symlink limits) | hardening | Counter 2 |
| C-P5 | construct archive evidence helper | hardening | H5 optional |

## Pending — autogenesis

| ID | Item | Class | Notes |
|----|------|-------|-------|
| A-P1 | Hard enforce activation card (refuse path without card) | hardening | Still convention |
| A-P2 | Auto-run construct on implement when scenario exists (operational habit) | discipline | Gate text shipped; needs consistent practice |
| A-P3 | Match path_modules_loaded to FS log when workspace present | hardening | Bridge activation proof |
| A-P4 | Questioning one-at-a-time as durable skill improvement | optional | Experience exists |

## Pending — agent-brain

| ID | Item | Class | Notes |
|----|------|-------|-------|
| B-P1 | **dream** path (uses construct) | new-surface / new path | Backlog since v0.1 |
| B-P2 | **think** / **forget** / **decide** | new-surface | Backlog since v0.1 |
| B-P3 | ADR-001 infinite conflict loops | design | Open |
| B-P4 | ADR-002 cross-repo joint fixes | design | Open |
| B-P5 | Unresolved-task list query UX | hardening | Thin |
| B-P6 | LLM-as-judge harvest quality | deferred | Post-v1 |
| B-P7 | Full E2E docker train under handover contract | eval | Scenario v4 + run |

## Pending — mesh / okf-wiki

| ID | Item | Notes |
|----|------|-------|
| M-P1 | L3 mesh depth / more hops productisation | Partial |
| M-P2 | Dead edges hygiene in scenarios | Ongoing |

## Pending — knowledge-crawl

| ID | Item | Notes |
|----|------|-------|
| K-P1 | Playwright auth strategies fully productised | Designed earlier; partial |
| K-P2 | Git crawl provenance + diff updates | Designed |

## Priority suggestion

1. C-P1 scenario v4 (bake E2E rules into construct)  
2. B-P7 run E2E under that scenario  
3. B-P1 dream when ready  
4. C-P2 write events if isolation audits need positive proof

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
