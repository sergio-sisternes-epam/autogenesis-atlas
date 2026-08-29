---
type: experience
title: "DECISION: Construct train-eval hardenings H1\u2013H6 + activation ledger"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Plan construct-train-eval-hardenings-2026-08-21. Five Docker-train follow-ups plus deterministic activation.jsonl. Construct becomes source of truth for skill/path/module load."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/challenge-adversarial-construct.md
    kind: related
  - path: autogenesis/decisions/reevaluate-handoff-loop.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-construct-eval-hardenings-decision`.

## What happened

**Plan:** `artifacts/autogenesis-plans/construct-train-eval-hardenings-2026-08-21.md`  
**Status:** design ready — stops for approve before implement.

## Origin

Docker Train construct run (`train-docker-mesh-v1` v2, workspace `run-044608abcc`):

- Contract + mesh **passed**
- Autogenesis claimed challenged_plan without loading reevaluate path (narrative-only honesty)
- Dead mesh edge to knowledge-crawl
- Stage counts approximate; inventory is ground truth
- Need deterministic skill/path/okf-wiki **file activation**

## Locked direction (H1–H6)

| ID | Direction |
|----|-----------|
| **H1** | Harden train-report / expects for Autogenesis path honesty |
| **H2** | Scenario v3: fix or remove dead `project-to-knowledge-crawl` edge |
| **H3** | Inventory minima smoke on target package (raw/knowledge floors) |
| **H4** | docker SKILL.md promotion remains **human-approved** Autogenesis implement only |
| **H5** | Copy evidence then destroy workspace (ops; optional archive later) |
| **H6** | **Deterministic `activation.jsonl` ledger**; construct smoke `type: activation-log`; ledger is source of truth over self-report |

## H6 principle

Agents must not be the sole auditors of what they loaded.  
Load events append to `<workspace>/activation.jsonl`; construct validates.  
Helper: `construct log-activation`. Callers (agent-brain train, later okf-wiki modules) append on intentional path/module load.

## Versions (on implement)

- construct **0.2.0**
- agent-brain **0.3.3**

## Not in this slice

OS-level read_file interception; LLM-as-judge; auto-promote docker skillmd.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
