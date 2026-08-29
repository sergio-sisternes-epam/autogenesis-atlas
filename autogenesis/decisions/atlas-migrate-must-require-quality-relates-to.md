---
type: decision
title: "atlas-migrate must require thorough relationship review and quality relates_to before Exit"
created: 2026-08-23
work_id: atlas-migrate-relationship-review-gate-v1
status: proposed
description: "Normative decision arising from skill-feedback blocker: bulk claim conversion with only generic self-referential relates_to is insufficient. A thorough relationship review producing quality links is mandatory; quality must be visible at compile / Exit."
tags: [decision, atlas-migrate, quality, relates_to, process]
relates_to:
  - path: autogenesis/work/atlas-migrate-relationship-review-gate-v1.md
    kind: implements
  - path: autogenesis/experiences/2026-08-23-atlas-migrate-relationship-review-defect.md
    kind: derived_from
---

## Decision

The `atlas-migrate` path (and supporting workflow-discipline language) must treat thorough relationship review and quality `relates_to` mesh as a non-skippable Change gate before Exit.

### Minimum quality bar (initial)

- Every decision page has ≥1 incoming edge from an experience or work hub (`implements`, `derived_from`, or `related`).
- Experiences that clearly realise a decision name that decision in `relates_to`.
- No claim-bearing page may leave Exit with *only* a self-referential link back to the migration experience.
- Path receipt must record `relationship_review: yes` and a count of quality edges added.

### Implementation direction

- Agent performs structured analysis (Atlas query + proposal of edges) and surfaces a short summary for user confirmation before Exit.
- Later optional strengthening of `atlas compile` quality checks is allowed but not required for the first fix.

## Rationale

User classified the missing review as a process defect and blocker. Future migrations (construct, apm, medium, portfolio, \ldots) would repeat the same shallow linking unless the path itself is corrected.
