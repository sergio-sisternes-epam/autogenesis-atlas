---
type: work
title: "Add thorough relationship-review + quality relates_to gate to atlas-migrate"
created: 2026-08-23
work_id: atlas-migrate-relationship-review-gate-v1
status: done
description: "Process defect fix: atlas-migrate must perform a thorough review of relationships between migrated documents and produce quality relates_to links before Exit. Captured from skill-feedback blocker after agent-brain migration."
relates_to:
  - path: autogenesis/experiences/2026-08-23-atlas-migrate-relationship-review-defect.md
    kind: records
  - path: autogenesis/decisions/atlas-migrate-must-require-quality-relates-to.md
    kind: related
  - path: autogenesis/plans/atlas-migrate-relationship-review-gate-v1.md
    kind: implements
---

## Scope

- Capture the defect (experience) and the normative decision.
- Design the new mandatory gate in `atlas-migrate` (and workflow-discipline if needed).
- Implement the gate.
- Test adherence on the next migration (construct or subsequent).

## Status

done (2026-08-23)

## Outcomes

- Gate implemented in atlas-migrate.md and SKILL.md v0.3.5
- Experience: 2026-08-23-implement-atlas-migrate-relationship-review-gate-v1

## Linked notes

- Skill-feedback report (conversation, 2026-08-23) — defect classified as incorrect-behaviour + missing-capability, severity blocker.
- User instruction: “capture this memory in autogenesis and open a formal work item, linking both notes. Then proceed with design. Once implementation is complete, we will test adherence here in the next migration.”
