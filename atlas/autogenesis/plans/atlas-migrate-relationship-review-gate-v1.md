---
type: plan
title: "Add thorough relationship-review + quality relates_to gate to atlas-migrate"
created: 2026-08-23
work_id: atlas-migrate-relationship-review-gate-v1
status: done
change_class: new-surface
subject: autogenesis
description: "Mandatory non-skippable gate in atlas-migrate: thorough relationship review producing quality relates_to edges before Exit. Path receipt gains relationship_review and quality_edges_added."
relates_to:
  - path: autogenesis/work/atlas-migrate-relationship-review-gate-v1.md
    kind: implements
  - path: autogenesis/decisions/atlas-migrate-must-require-quality-relates-to.md
    kind: related
  - path: autogenesis/experiences/2026-08-23-atlas-migrate-relationship-review-defect.md
    kind: derived_from
---

## Intent + scope

Add a non-skippable Change gate to the `atlas-migrate` path so that every migration performs a thorough review of relationships between the newly claimed pages and produces quality `relates_to` edges before Exit. The gate must be visible in the path receipt (`relationship_review: yes` + edge count) and must prevent Exit while only generic self-referential migration links exist.

## Non-goals

- Changing the mechanical `atlas migrate` / promote / compile CLI behaviour.
- Requiring perfect denseness on every single page.
- Strengthening `atlas compile` itself in this work_id (optional follow-on).
- Re-migrating already-completed subjects except as the adherence test after implementation.

## Pins

1. The review is mandatory and non-skippable.
2. Minimum quality bar: every decision has ≥1 incoming edge from an experience or work hub; experiences that realise a decision name it; no page leaves Exit with only a self-referential migration link.
3. Agent proposes; user confirms (or explicitly waives with recorded reason).
4. Path receipt records the review and edge count.
5. Test adherence on the next migration after implement.

## Genesis Artifacts

### Intent + scope + non-goals
See above (mini-genesis for new-surface).

### Diagrams / interface
Sequence: mechanical migrate → claim conversion → structured relationship analysis → user summary → write quality edges → compile green → discipline rewrite + receipt with relationship_review: yes.

### Cost note
Moderate token cost on large corpora; acceptable because the gate is the point of the change.

## Acceptance

- `atlas-migrate.md` contains an explicit, non-skippable “Thorough relationship review” step with the minimum quality bar.
- Path receipt schema updated.
- Workflow-discipline aligned if it restates the pins.
- Plan + work node linked and compile green.
- After implement, the next real migration must demonstrate the gate was followed.

## Catalogue Review
n/a (process-gate addition; no topology / activation-card / multi-agent change).

## Residual risks
- Over-strict bar could slow large migrations; initial bar is deliberately pragmatic.
- Agent-proposed edges may need human correction; confirmation step mitigates.

## Stop for approval

Explicit user approval of work_id `atlas-migrate-relationship-review-gate-v1` received 2026-08-23. Implement may proceed.
