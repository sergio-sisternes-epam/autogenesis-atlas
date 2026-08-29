---
type: experience
title: "Implement: autogenesis-patterns-as-genesis-extension-v1"
created: 2026-08-23
work_id: autogenesis-patterns-as-genesis-extension-v1
status: raw
description: "Collapsed parallel catalogue to B17 ACTIVATION CARD only; patterns module is now the extension injector; genesis remains read-only"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: work/autogenesis-patterns-as-genesis-extension-v1.md
    kind: implements
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-23-implement-patterns-as-genesis-extension-v1`.

## What happened

Implemented the approved plan for work_id `autogenesis-patterns-as-genesis-extension-v1`.

## Changed files

- `references/modules/patterns.md` — rewritten as thin extension injector (version 0.4.0)
- `references/modules/patterns/activation-card.md` — re-homed as B17, classical analog added, version 0.2
- `references/modules/patterns/triage-panel.md` → moved to `patterns/deprecated/`
- `references/modules/patterns/panel-review.md` → moved to `patterns/deprecated/`
- `references/paths/design.md` — Catalogue Review and description updated for mandatory injection of B17
- `references/scenarios/patterns-as-genesis-extension-adversarial-v1.yaml` — created
- `references/wiki/knowledge/concept-patterns-module.md` — updated to extension-injector description
- `references/wiki/knowledge/decision-patterns-extend-genesis-catalogue-review.md` — updated to new locked decision

## Construct evaluation

Deferred: adversarial scenario file created; full construct run left for a later evaluation pass. No red smokes claimed or waived.

## Acceptance check

- [x] Only Activation Card / B17 remains
- [x] Triage Panel and Panel Review deprecated
- [x] patterns.md is the extension injector with mandatory load-on-genesis rule
- [x] activation-card.md carries B17 identity
- [x] Design path updated
- [x] No files inside the genesis skill were modified
- [x] Adversarial scenario present

## Related

- Plan: artifacts/autogenesis-plans/2026-08-23-autogenesis-patterns-as-genesis-extension-v1.md
- [[knowledge/concept-patterns-module]]
- [[knowledge/decision-patterns-extend-genesis-catalogue-review]]

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
