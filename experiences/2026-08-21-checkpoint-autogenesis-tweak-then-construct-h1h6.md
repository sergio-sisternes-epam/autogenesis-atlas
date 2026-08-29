---
type: experience
title: "CHECKPOINT: Autogenesis discipline tweak first, then redo construct H1\u2013H6"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "IMPORTANT resume point. (1) Implement autogenesis change-class + construct Exit + path-load. (2) Only then redo construct train-eval hardenings plan with mini-genesis for H6. Do not implement H1\u2013H6 under the old packet."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/challenge-adversarial-construct.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-checkpoint-autogenesis-tweak-then-construct-h1h6`.

## What happened

## Why

Docker train construct judgment showed under-design risk: follow-up “plans” skipped genesis depth for new surfaces (activation ledger). User chose:

1. **First** — plan/implement **autogenesis** discipline tweak  
2. **Then** — **redo** construct enhancement plan (H1–H6) under the new rules  
3. Memory checkpoint so a later session can resume without re-deriving order

## Step 1 — Autogenesis tweak (active plan)

**Plan:** `artifacts/autogenesis-plans/autogenesis-change-class-and-construct-exit-2026-08-21.md`

Deliver:

- Change-class: `hardening` | `new-surface` | `new-skill`
- Mini-genesis required for `new-surface` (mermaid + interface sketch + cost note)
- Construct-aware Exit checklist
- Path-load rule when reevaluate / challenged_plan claimed
- autogenesis **0.2.1**

**Status:** SHIPPED autogenesis **0.2.1** (2026-08-21). Step 1 done. Proceed Step 2: redo construct H1–H6 plan.

## Step 2 — Redo construct H1–H6 (deferred)

**Old packet (supersede after Step 1):**  
`artifacts/autogenesis-plans/construct-train-eval-hardenings-2026-08-21.md`  
**Old decision:** `[[raw/experiences/2026-08-21-construct-eval-hardenings-decision]]`

On resume:

1. Confirm autogenesis 0.2.1 shipped  
2. Re-classify H1–H6 under change-class (H6 = new-surface → mini-genesis)  
3. Write **new** plan file (do not only edit old without mini-genesis for H6)  
4. Approve → implement construct 0.2.0 + agent-brain train/report hooks

## Do not

- Implement activation ledger under the pre-tweak packet alone  
- Mark H1–H6 done without redoing the plan  
- Skip change-class on the redo  

## Related context

- Docker train workspace evidence: `/tmp/construct-workspaces/run-044608abcc` (may still exist)  
- Scenario: `train-docker-mesh-v1` v2  
- Construct train-report contract already in 0.1.1  


**Update 2026-08-21:** Step 2 complete — construct 0.2.0 FS monitor implemented (plan construct-fs-activation-monitor).

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
