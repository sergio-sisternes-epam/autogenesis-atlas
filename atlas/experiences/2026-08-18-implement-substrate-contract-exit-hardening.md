---
type: experience
title: "Implemented substrate-contract hardening for Exit (okf-wiki / okf) and design path"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Applied approved plan: Exit activation checklist, extended path receipt, design-path language rewritten to full substrate contract, remaining absolute path removed from review-package."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-implement-substrate-contract-exit-hardening`.

## What happened

## What the user asked

> approved. Proceed with implementation to fix the okf-wiki problem

## What was done (Change)

Applied the approved design plan under G4/G5:

1. **Root SKILL.md**
   - EXIT section rewritten to full multi-harness substrate contract for skills named `okf-wiki` and `okf`.
   - Added explicit Exit activation checklist that must be emitted before claiming Exit complete.
   - Path receipt extended with `nested_skills_loaded` and `substrate_contract: applied | missing`.
   - Design row in capabilities table updated to substrate-contract wording.

2. **references/paths/design.md**
   - Description and procedure steps 1–2 rewritten: “Apply substrate contract to skill named `genesis` / `think-challenge`”.
   - Exit section now points to the root checklist.
   - Approval presentation must follow the agreed template (from prior memory).

3. **references/paths/implement.md**
   - Exit step rewritten to the same substrate-contract form.

4. **references/paths/review-package.md**
   - Hard-coded absolute path to the nesting knowledge page removed; replaced with path-resilient reference.

5. **Knowledge pages**
   - `design-path-sequence.md` and `progressive-disclosure-paths.md` updated to match.

## Version / content identity

- Content identity: 2026-08-18 substrate-contract Exit + design hardening
- No auto-wiring performed
- Scope limited to the approved pins

## Related

- Continues [[raw/experiences/2026-08-18-skill-nesting-read-file-invocation-discovery]]
- Continues [[raw/experiences/2026-08-18-path-resilient-nesting-contract]]
- Continues [[raw/experiences/2026-08-18-approval-plan-must-use-agreed-template]]
- Implements the plan that closed the residual abbreviated Exit language

## Durable conclusions claimed

- Exit of every path must now apply the substrate contract to `okf-wiki` and `okf`.
- Path receipt is incomplete without `nested_skills_loaded` and `substrate_contract`.
- Design path must activate genesis and think-challenge via the same contract.
- These are lasting procedural rules.

## Ingest decision

**wiki-ingest required** (durable procedure changes were implemented). Will be performed after this remember.

## Path context

```text
subject: autogenesis
path: implement
approved: yes
okf_wiki_root: autogenesis/references/wiki
nested_skills_loaded: okf-wiki, okf
substrate_contract: applied
remember: yes
ingest: yes
Enter|Change|Exit: pass
```

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
