---
type: experience
title: "Patterns module full arc: discussion \u2192 design \u2192 implement"
created: 2026-08-22
work_id: autogenesis-patterns-module-v1
status: raw
description: "End-to-end memory of creating the progressive patterns module under autogenesis: locks, capabilities pin, think-challenges, design plan, approval, implement of template + Activation Card + six v1 capabilities"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: work/autogenesis-patterns-module-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/challenge-adversarial-construct.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-22-patterns-module-full-arc`.

## What happened

Consolidating memory of the complete path from discussion through design to implement for work_id `autogenesis-patterns-module-v1`.

## What the user asked for

Discuss creation of a new subskill/module to contain the definition and creation of patterns; incorporate the Activation Card as the first pattern; include a pattern template; search online for standards; use think-challenge before sharing; explore location, admission, template, scope, and capabilities one at a time; then formal design and implement after approval.

## Discussion locks (in order)

1. **Location** — Progressive module under autogenesis (not new root skill, not okf-wiki-only knowledge first).
2. **Admission bar** — Proven use first. A pattern is a generalisation of a common solution that repeats over time and works. No speculation-first catalogue.
3. **Template** — Keep the candidate template as v1. Known uses is a living section so Autogenesis can record where the pattern has been applied and how it is working.
4. **Scope** — Active capability (not docs-only): Identify, Extract, Create, Record known-use, Load, List/query.

## Capabilities after think-challenge

**Kept for v1**

| Capability | Constraint |
|------------|------------|
| Identify | Flags candidates only; does not create |
| Extract | Draft only; admission still proven repeated use; must cite specific repeated experiences |
| Create | Requires evidence of *repeated* use before status: active |
| Record known-use | Cheap; living Known uses; ideally tied to remember/Exit |
| Load | Progressive by id/category — never full catalogue dump |
| List/query | Progressive |

**Deferred (explicit, so not forgotten)**

- **Scan/detect** — false-candidate risk; pattern-mining precision problems  
- **Relate** — pattern-language graph; not needed while catalogue is small  

Decision page: [[knowledge/decision-patterns-module-v1-capabilities]]  
Pin experience: [[raw/experiences/2026-08-22-patterns-module-discussion-capabilities-pin]]

## Design

- Plan: `artifacts/autogenesis-plans/2026-08-22-autogenesis-patterns-module-v1.md`
- change-class: new-surface (mini-genesis)
- Work node: [[raw/experiences/work-autogenesis-patterns-module-v1]]
- think-challenge of the plan: [[raw/experiences/2026-08-22-challenge-patterns-module-v1-plan]]
  - Residual risks accepted: prose-only Create bar; “active” = procedures + file writes; cross-skill load via substrate; Extract must not become Scan
- User: keep plan as-is; document challenge as memory → then **Approved**

## Implement (shipped)

| File | Role |
|------|------|
| `references/modules/patterns.md` | Entrypoint: definition, admission, catalogue, six capability procedures, deferred list |
| `references/modules/patterns/template.md` | Canonical template v1 |
| `references/modules/patterns/activation-card.md` | First pattern with Known uses from real Runs |
| `references/scenarios/patterns-module-adversarial-v1.yaml` | Adversarial smokes (construct deferred) |

Implement experience: [[raw/experiences/2026-08-22-implement-patterns-module-v1]]

## First pattern: Activation Card

Documents the Enter card → Change → path receipt / Exit discipline already used by autogenesis and okf-wiki. Known uses seeded from this conversation’s design/implement arcs and the type-normalise gate work.

## Construct

Scenario file present. Full construct evaluation **deferred** (no red claimed or waived).

## Outcome

Patterns module is live under autogenesis. Catalogue has one active pattern. Admission and deferred capabilities are written so future Runs do not re-litigate or accidentally implement Scan/Relate in v1.

## Related lineage

- [[knowledge/decision-patterns-module-v1-capabilities]]
- [[raw/experiences/2026-08-22-patterns-module-discussion-capabilities-pin]]
- [[raw/experiences/2026-08-22-challenge-patterns-module-v1-plan]]
- [[raw/experiences/2026-08-22-implement-patterns-module-v1]]
- [[raw/experiences/work-autogenesis-patterns-module-v1]]
- [[knowledge/discipline-enter-change-exit]]
- okf-wiki side: type-normalise application gate and process-discipline concern (same day)

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
