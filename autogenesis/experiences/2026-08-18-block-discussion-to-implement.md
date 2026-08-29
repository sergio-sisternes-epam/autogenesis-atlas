---
type: experience
title: "2026-08-18 Implement: block discussion \u2192 implement short-circuit"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Hard-wired the rule that discussion never transitions directly to implement; only formal design \u2192 persisted challenged plan \u2192 explicit approval \u2192 implement is legal."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/challenge-adversarial-construct.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-block-discussion-to-implement`.

## What happened

## What the user asked
- Agreed to keep discussion mode as-is (no mandatory think-challenge inside discussion).
- Instructed that the agent must block any attempt to go from discussion straight to implement.
- Required the formal design path first; acknowledged past accidental short-circuits as incorrect.
- Later: “proceed with the design”, then approved the full plan and pinned decisions.

## What was done
Implemented the approved plan `artifacts/autogenesis-plans/2026-08-18-block-discussion-to-implement.md`.

## Changed files
- `artifacts/autogenesis-plans/2026-08-18-block-discussion-to-implement.md` (created – formal design plan)
- `SKILL.md` (updated – Enter rule 4 + Hard boundaries table)
- `references/paths/implement.md` (updated – When (Change) G4 strengthened)
- `references/wiki/knowledge/block-discussion-to-implement.md` (created)
- `references/wiki/index.md` (updated)
- `references/wiki/raw/experiences/2026-08-18-block-discussion-to-implement.md` (this file)

## Pinned decisions (from approved plan)
1. Discussion mode never has implement authority and never transitions directly to implement.
2. Implement is legal only after a persisted plan produced by formal design (genesis → internal think-challenge → pin → C1–C5) is explicitly approved.
3. Any jump is refused; agent re-issues Enter for formal design.
4. Rule recorded as durable knowledge.
5. No emergency-override flag in this change.

## Outcome
The short-circuit that previously allowed discussion sketches to become product changes after a casual “Approved” is now an explicit incomplete condition. Future Runs cannot silently re-introduce it.

Related: [[knowledge/block-discussion-to-implement]], [[knowledge/discipline-enter-change-exit]], [[knowledge/core-process]].

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
