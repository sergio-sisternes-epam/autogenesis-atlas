---
type: experience
title: "When asking for approval the plan must be presented in the agreed template"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Observation that design-path approval stop requires presenting the full pinned plan to the user using the agreed template, not a free-form summary or deferred file path."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-approval-plan-must-use-agreed-template`.

## What happened

## What the user asked

> autogenesis skill capture a memory for a future review based on this memory: When asking for approval, the plan should be presented to the user in the agreed template.

## What happened in the preceding design run

In the design path for “activation paths consistency”:

1. The Enter card and Change work were performed.
2. At the approval stop the agent first emitted only the five pinned decisions + a promise that the plan would live at `artifacts/autogenesis-plans/…`.
3. The concrete plan (exact textual replacements) was not shown until the user asked “what is the plan? Why have you not shared with me for review?”
4. Only then was the full plan written and presented.

This is the behaviour that must not recur.

## Pinned observation (for future review)

**Rule:** When a design path reaches the approval stop, the pinned plan **must be presented to the user in the agreed template** in the same turn that requests approval.

**Agreed template (minimum required content at the approval stop):**

- Pinned decisions (visible list)
- Challenge-success criteria C1–C5 table
- Exact scope of changes (file-by-file / section-by-section)
- Non-goals
- Explicit “waiting for your approval” statement
- Path receipt

The persisted file under `artifacts/autogenesis-plans/` may use any internal structure; the **user-facing presentation** at the approval hinge is what this experience constrains.

## Related

- Continues the activation-discipline and progressive-disclosure work:  
  [[raw/experiences/2026-08-18-path-resilient-nesting-contract]]  
  [[raw/experiences/2026-08-18-progressive-disclosure-implemented]]  
  [[raw/experiences/2026-08-16-run-design-path-sequence-implemented]]
- Design path procedure: `references/paths/design.md` and knowledge `design-path-sequence.md`
- Challenge-success criteria: `references/challenge-success-criteria.md`

## Disposition

- Status: `unverified` (behaviour observation from this session)
- No product-file changes were made in the reflect-challenge path
- Intended for a future design or review path that may promote this rule into the design-path procedure itself (so the presentation template becomes an enforceable part of G7 / approval stop)
- Ingest: **explicit defer** — this is a process observation recorded for future review; no durable procedure change is claimed in the present Run

## Path context

```text
subject: autogenesis
path: reflect-challenge
approved: n/a
okf_wiki_root: autogenesis/references/wiki
remember: yes
ingest: defer: process observation for future review; no durable procedure claimed yet
Enter|Change|Exit: pass
```

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
