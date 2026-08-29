---
type: experience
title: Implement sole-producer rule for behavioural contracts
work_id: 2026-08-25-specify-only-behavioural-contract
implements: 2026-08-25-specify-only-behavioural-contract
closes: []
plan_path: autogenesis/plans/2026-08-25-specify-only-behavioural-contract.md
construct_eval: deferred
origin: internal
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-08-25-specify-only-behavioural-contract.md
    kind: implements
  - path: autogenesis/plans/2026-08-25-specify-only-behavioural-contract.md
    kind: implements
---

# Experience: implement specify-only behavioural contract

## What changed

Applied the approved plan `2026-08-25-specify-only-behavioural-contract`.

## Changed files

- `references/paths/design.md` — step 6b rewritten to sole-producer rule; direct authoring of `.feature` files forbidden; activation-card hint required; ownership sentence added.
- `references/modules/workflow-discipline.md` — activation-card schema extended with `behavioural_contract:` hint; discussion principles updated (may explore via specify in discussion mode; only design materialises the contract).
- `references/scenarios/specify-only-adversarial-v1.yaml` — new adversarial suite materialised from the design draft.
- `references/atlas/autogenesis/plans/2026-08-25-specify-only-behavioural-contract.md` — plan persisted (status approved).
- `references/atlas/autogenesis/work/2026-08-25-specify-only-behavioural-contract.md` — work node created and left at implementing → done.

## Construct evaluation

Deferred: this is a procedural / design-path change. No existing Construct fixtures cover the design-path text itself. The new adversarial YAML is present for future Construct runs; deterministic file checks (presence of sole-producer wording, hint in card schema, scenario file) are satisfied by the edits above.

## Notes

Ownership is now clear: agent-spec path `specify` is the only writer of behavioural Gherkin. Autogenesis consumes the resulting contract section or records an explicit deferred reason.
