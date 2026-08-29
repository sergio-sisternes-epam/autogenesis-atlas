---
type: decision
title: "Enhancement \u2014 think-challenge to adversarial construct"
created: 2026-08-21
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Gate: grounded and named-theory counters become construct smokes that fail over-eager behaviour. Implemented in autogenesis 0.3.0."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/challenge-adversarial-construct.md
    kind: related
  - path: autogenesis/decisions/adversarial-construct-learnings.md
    kind: related
  - path: autogenesis/decisions/adversarial-construct-future-actions.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

**work_id:** `autogenesis-challenge-adversarial-construct` (A-P-ADV)  
**Priority:** high  
**Status:** implemented (autogenesis v0.3.0)

## Rule

1. think-challenge gathers search counters, then derives additional smokes from named theories / model knowledge. Each smoke names its source. Empty suite forbidden on behaviour change.
2. Design emits a full construct scenario draft. Implement fills paths/commands and may add smokes; it must not drop approved smokes without a new design.
3. File: `<subject>/references/scenarios/<capability>-adversarial-vN.yaml` (new file + bump; keep prior).
4. Implement Exit runs adversarial + happy-path. Waive a red smoke only if that named counter is out of scope.
5. Construct MUST NOT invoke autogenesis (R1). Autogenesis may call construct CLI after implement (R2).
6. Fixtures are eval-only; live skill must not be mutated.

## Learnings (after v2)

Phrase-presence is not the gate. See [[knowledge/adversarial-construct-learnings]].

## Provenance

First worked example: agent-brain dream 0.4.0, `dream-adversarial-v1`. Plan: `artifacts/autogenesis-plans/2026-08-21-autogenesis-challenge-adversarial-construct.md`.
