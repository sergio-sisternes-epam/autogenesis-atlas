---
type: experience
title: "Design: activation card as optional/debug for any skill + review-package check"
created: 2026-08-22
work_id: autogenesis-activation-card-extend
status: raw
description: "Formal design Run for work_id autogenesis-activation-card-extend; mini-genesis plan persisted; stopped for approval"
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/work/autogenesis-activation-card-extend.md
    kind: implements
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-22-design-activation-card-extend`.

## What happened

## What the user asked
- Original: how the card system works; extend as optional/debug on/off for any skill/agent.
- Clarifications: apply the pattern when creating new issues/skills; include a check in review-package for card presence.
- Final: “proceed to design”

## What was done
- Re-issued Enter card as mode: run, path: design, subject: autogenesis.
- Classified change-class: **new-surface**.
- Assigned **work_id: autogenesis-activation-card-extend**.
- Applied substrate contract to genesis (depth = mini-genesis).
- Loaded internal think-challenge; grounded counters via web search (progressive disclosure, workflow gates, skill validators).
- Produced and persisted plan at `artifacts/autogenesis-plans/2026-08-22-autogenesis-activation-card-extend.md`.
- Pinned decisions: default=off for new skills; check inside existing gate-map facet; no hard enforce outside Autogenesis; harness-agnostic frontmatter.
- Drafted adversarial scenario `activation-card-extend-adversarial-v1`.
- Stopped for explicit approval (G7).

## Changed files
- artifacts/autogenesis-plans/2026-08-22-autogenesis-activation-card-extend.md (created)
- [[raw/experiences/2026-08-22-design-activation-card-extend]] (this file)

## Pinned decisions
1. New skills get declaration present but start `activation_card: off`.
2. Card check extends `validate-gate-map-and-non-goals` (no new facet).
3. A-P1 remains separate; this supplies the general surface.
4. Front-matter only.

## Related
- [[knowledge/pending-backlog-active]] (A-P1 autogenesis-activation-card-enforce)
- [[knowledge/discipline-enter-change-exit]]
- [[knowledge/path-modules-and-gates]]
- [[knowledge/implementation-status-2026-08-21]]

## Ingest deferral
ingest: defer: design only — no durable knowledge-page creation or material update in this Run; plan and experience only. Will ingest conclusions after implement if approved.

## Path receipt
```text
subject: autogenesis
path: design
approved: no
okf_wiki_root: autogenesis/references/wiki
nested_skills_loaded: genesis; okf-wiki (wiki-lineage-autogenesis, wiki-remember); okf (pending full)
substrate_contract: applied
remember: yes (this experience)
ingest: defer: design only; no durable knowledge pages yet
Enter|Change|Exit: Enter pass; Change pass (G3/G7); Exit pass (lineage recorded)
```

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
