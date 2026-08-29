---
type: experience
title: "Implemented multi-harness skill-nesting contract + review-package path"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Approved plan executed: substrate contract + per-harness mapping made mandatory in Autogenesis; new review-package path; knowledge, SKILL.md, design.md, implement.md and core-process updated."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-implement-skill-nesting-multi-harness`.

## What happened

## What the operator approved

The design plan at `artifacts/autogenesis-plans/2026-08-18-skill-nesting-invocation-and-review.md` (including the multi-harness substrate refinements demonstrated in skill-test-a).

## What was implemented

1. Knowledge page updated to the full multi-harness substrate contract + mapping table:  
   `references/wiki/knowledge/skill-nesting-invocation-pattern.md`

2. New path module:  
   `references/paths/review-package.md`  
   (dual-mode: substrate audit always; harness-mapping audit when targets declared). Advisory only.

3. Main `SKILL.md`:
   - Added `review-package` row to Capabilities table.
   - Added permanent “Skill chaining rule (mandatory)” section pointing at the knowledge page.

4. Light patches:
   - `paths/design.md` — chaining designs must include the substrate contract.
   - `paths/implement.md` — verify contract (or run review-package) when chaining is present.
   - `knowledge/core-process.md` — references the new rule and review path.

5. Validated: autogenesis skill still passes `validate-skill.sh`.

6. Real-task check: skill-test-a already contains the full portable pattern and would report `pass` under review-package.

## Durable conclusion (to ingest)

The multi-harness skill-nesting substrate contract is now mandatory for any skill body or path module grown or reviewed by Autogenesis. The single source of truth is `knowledge/skill-nesting-invocation-pattern.md`. The `review-package` path is the operational audit mechanism.

## Related

- Continues [[raw/experiences/2026-08-18-skill-nesting-read-file-invocation-discovery]]
- Implements the approved plan for subject autogenesis

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
