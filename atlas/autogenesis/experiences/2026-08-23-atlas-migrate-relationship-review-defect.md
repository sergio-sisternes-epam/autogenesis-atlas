---
type: experience
title: "Defect: atlas-migrate bulk claim conversion skipped thorough relationship review"
created: 2026-08-23
work_id: atlas-migrate-relationship-review-gate-v1
status: closed
description: "User feedback (via skill-feedback) that the agent-brain atlas-migrate performed only minimal generic relates_to links. Thorough review of relationships between documents and quality-link creation during compilation are required. This is a process defect in atlas-migrate."
tags: [defect, atlas-migrate, relationship-review, skill-feedback, blocker]
relates_to:
  - path: autogenesis/work/atlas-migrate-relationship-review-gate-v1.md
    kind: implements
  - path: autogenesis/decisions/atlas-migrate-must-require-quality-relates-to.md
    kind: related
---

## Context

After completing the pragmatic bulk migration of agent-brain (9 decisions + 78 experiences with only generic self-referential relates_to), the user asked for confirmation that a deep review of relationships between documents had been performed. The agent correctly stated that it had not. The user then filed skill-feedback against autogenesis, classifying the omission as a defect and a blocker.

## What happened

- atlas-migrate path pins require “full claim conversion” and relates_to with autogenesis/… paths, but do not currently mandate *quality* or *density* of those links, nor an explicit thorough-review gate.
- Result: minimal linking was treated as compliant; user rejects that interpretation.
- Skill-feedback report produced (incorrect-behaviour + missing-capability, severity blocker).
- User instruction: capture this memory in autogenesis, open a formal work item linking both notes, then proceed with design. Once implementation is complete, adherence will be tested on the next migration.

## Outcome

Memory captured. Formal work item opened. Design of the relationship-review gate is the next step under this work_id.

## Follow-ups

- Design + implement the mandatory thorough relationship review + quality-link gate in atlas-migrate.
- Re-test adherence on the next subject migration (construct or subsequent).
- Optionally strengthen atlas compile quality checks later.
