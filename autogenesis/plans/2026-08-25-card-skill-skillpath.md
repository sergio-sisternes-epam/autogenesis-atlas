---
type: plan
title: "Card template includes skill and skill_path as first values"
created: 2026-08-25
work_id: 2026-08-25-card-skill-skillpath
status: done
change_class: hardening
subject: autogenesis
description: "Enhance the canonical activation-card (Enter + path receipt) so skill and skill_path appear as the first two fields; propagate the updated template to every skill and path that documents the card."
origin: internal
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-08-25-card-skill-skillpath.md
    kind: implements
---

## Intent + scope

Make the canonical activation-card template (and every path receipt) begin with the two fields that identify *which skill is activating*:

```text
skill: <activating skill name>
skill_path: <resolved path to that skill’s root directory>
```

These become the first two lines of **any** card (Enter or path receipt). All subsequent fields remain unchanged and in their existing order.

## Non-goals

- No new front-matter keys, no change to `activation_card: on|off|debug` semantics.
- No automatic enforcement outside skills that already declare the card.
- No rewrite of historical experiences or old receipts.

## Pins

1. `skill` = the skill whose `activation_card` (or equivalent discipline) is currently driving the Run (normally the skill that emitted the card).
2. `skill_path` = the absolute (or harness-resolved) path to that skill’s root directory (the directory that contains `SKILL.md`).
3. Both fields appear **first**, before `mode`.
4. Path receipts receive the same two leading fields for lineage symmetry.
5. Propagation is a pure documentation/template update; no peer skill is given new runtime authority.

## Genesis Artifacts

### Intent + scope + non-goals
(see above)

### Acceptance

- Canonical definition in `references/modules/workflow-discipline.md` updated.
- Pattern B17 (`references/modules/patterns/activation-card.md`) updated to match.
- Every skill that currently hard-codes or documents an Enter card / path receipt is updated to the new first-two-fields shape (or points at the canonical schema).
- No behavioural change to gates, mode rules, or substrate contract.
- Version bump on autogenesis (and any peer that receives a material card-text change).

## Residual risks

Agents that already emit cards from memory may lag one session; residual accepted for hardening.

## Stop for approval

Approved by user 2026-08-25.
