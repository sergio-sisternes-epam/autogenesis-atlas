---
type: experience
title: "Patterns + catalogue-review arc: completed work and pending"
created: 2026-08-22
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "End-of-arc memory: what shipped, what stays draft/deferred/held, and what is not pending."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-22-patterns-catalogue-arc-complete-and-pending`.

## What happened

Session date: 2026-08-22. Subject: autogenesis (with okf-wiki lineage earlier the same day).

## Completed (shipped or pinned)

### Patterns module (work_id autogenesis-patterns-module-v1)
- Progressive module under autogenesis: definition, proven-use admission, template v1, six v1 capabilities
- Deferred capabilities recorded: Scan/detect, Relate
- **Activation Card** pattern — **active**, Known uses seeded
- Decision: [[knowledge/decision-patterns-module-v1-capabilities]]
- Concept: [[knowledge/concept-patterns-module]]
- Full arc: [[raw/experiences/2026-08-22-patterns-module-full-arc]]

### Extracted operational drafts (not active)
- **Triage Panel** — draft v0.4 (`patterns/triage-panel.md`): bulk + event-driven (adopter chooses), human/AI authors, silence ≠ formal approval, thin vs full, dissent
- **Panel Review** — draft v0.2 (`patterns/panel-review.md`): advisory regime, fan-out + synthesizer, abstract finding weights; Blocker/NIT only as examples
- Decision on weights: [[knowledge/decision-panel-review-finding-weights]]
- User choice: **leave both as draft** until Known uses from practice

### Relationship to genesis
- Decision: [[knowledge/decision-patterns-extend-genesis-catalogue-review]]
- Patterns stay in autogenesis; genesis is read-only upstream
- Operational patterns **refine / use** genesis Tier-2/3 (e.g. A1 PANEL, B1 Fan-out + Synthesizer); no catalogue merge, no genesis edits
- Root skill promotion **held**

### Catalogue Review gate (work_id autogenesis-catalogue-review-gate-v1) — **done**
- `paths/design.md` step 5: Catalogue Review required when topology/gate/panel shaped; else `catalogue_review: n/a`
- `modules/patterns.md`: Design-time catalogue review procedure
- `workflow-discipline.md`: design path row updated
- Scenario: `scenarios/catalogue-review-gate-adversarial-v1.yaml` (construct deferred)
- Implement: [[raw/experiences/2026-08-22-implement-catalogue-review-gate-v1]]

### Earlier same-day lineage (okf-wiki / process)
- Type-normalise application gate and process-discipline concern (separate work nodes on okf-wiki)
- Activation Card discipline used across discussion → design → implement arcs

## Explicitly pending (not blocked)

| Item | State | Notes |
|------|--------|------|
| Triage Panel, Panel Review | **draft** | User: leave as draft; promote only after Known uses |
| Construct: patterns-module-adversarial-v1 | deferred | Scenario exists |
| Construct: catalogue-review-gate-adversarial-v1 | deferred | Scenario exists |
| Root skill agentic-patterns | **held** | Revisit when catalogue maturity criteria met |
| Scan/detect, Relate | **deferred** | v1 capabilities pin |
| Extra Known uses on Activation Card | optional hygiene | Append on future Runs |
| refines A1 / uses B1 on panel draft Related sections | optional polish | Can wait until promote |

## Explicitly not pending

- Open design path — none
- Failed validate — none
- Unpinned decision awaiting user — none
- Requirement to activate drafts on a deadline — none

## How to resume later

1. Fill Known uses on triage-panel / panel-review from real Runs → Create to active if admission bar met.  
2. Run construct on deferred scenario YAMLs when evidence is wanted.  
3. Any new topology/panel/gate design automatically hits Catalogue Review.  
4. Promotion to root skill only via new design path after maturity criteria.

## Related index

- [[knowledge/concept-patterns-module]]
- [[knowledge/decision-patterns-module-v1-capabilities]]
- [[knowledge/decision-patterns-extend-genesis-catalogue-review]]
- [[knowledge/decision-panel-review-finding-weights]]
- [[raw/experiences/2026-08-22-patterns-module-full-arc]]
- [[raw/experiences/2026-08-22-implement-catalogue-review-gate-v1]]
- [[raw/experiences/2026-08-22-extract-triage-panel-draft]]

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
