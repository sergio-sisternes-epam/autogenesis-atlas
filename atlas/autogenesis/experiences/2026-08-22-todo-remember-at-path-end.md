---
type: experience
title: "Todo: remember-at-path-end discipline"
created: 2026-08-22
work_id: autogenesis-remember-at-path-end
status: raw
description: "Skill-feedback driven backlog. Autogenesis should systematically remember at the end of discuss, design, implement, and construct testing \u2014 not only when the agent happens to."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/work/autogenesis-remember-at-path-end.md
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

Migrated from okf-wiki raw experience `2026-08-22-todo-remember-at-path-end`.

## What happened

## Source
Skill-feedback report: `artifacts/skill-feedback-autogenesis-memory-generation-2026-08-22.md`  
Triggered by user discovery that migration design memory was thin after a full design → implement cycle.

## Problem
Exit already requires `remember: yes`, but the **depth** of what is remembered is under-specified. Work nodes and implement experiences are reliable; full design-session narratives (pins, challenges, rationale) are optional in practice and were missing for `okf-wiki-migrate-type-v1` until the user asked.

## Proposed work_id
`autogenesis-remember-at-path-end`

## Suggested scope
1. Tighten `workflow-discipline.md` Exit checklist for **design** path: require a design-session narrative experience (or explicit one-line deferral with reason) linked to the work_id.
2. Keep implement’s existing `## Changed files` requirement.
3. For construct evaluation Runs: require a construct-eval experience (pattern already used today for ontology-type).
4. Optional: short template under `references/templates/`.
5. Optional construct smoke: design Exit without linked design-session experience → incomplete.

## Non-goals
- Remembering every micro-turn
- Changing okf-wiki remember semantics

## Related
- Feedback report path above
- Example gap: migrate-type design was recovered as [[raw/experiences/2026-08-22-migrate-type-design-session]] only after user request (okf-wiki store)

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
