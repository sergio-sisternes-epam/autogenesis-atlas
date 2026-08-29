---
type: decision
title: "Future actions \u2014 adversarial construct hardening"
created: 2026-08-22
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Open hardening actions after A-P-ADV 0.3.0: Exit latest-vs-all, shared checker, receipt field, suite-size review. Not shipped."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/challenge-adversarial-construct.md
    kind: related
  - path: decisions/adversarial-construct-learnings.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

Change-class if picked up: **hardening** (unless the checker grows a new CLI contract → `new-surface`). Do not implement from this page.

| work_id | Action | Why | Next |
|---------|--------|-----|------|
| autogenesis-adversarial-exit-latest | Exit runs **latest** `*-adversarial-vN`; keep prior as regression | v1 and v2 both exist; Exit never said which | design pin |
| autogenesis-adversarial-checker | Shared `check_adversarial_gate.py`; smokes print only `{"ok":true}` | v2 inline Python and invalid JSON | design pin |
| autogenesis-adversarial-receipt | Receipt field `adversarial_scenarios` | Lineage cannot name what ran | design pin |
| autogenesis-adversarial-suite-review | P12 size review on next behaviour-change design | every-counter + add-only | do in that design |

**Do not:** teach construct to invoke autogenesis (R1).

See [[knowledge/adversarial-construct-learnings]] and [[knowledge/pending-backlog-active]].

## Rationale

Migrated from okf-wiki knowledge page `adversarial-construct-future-actions` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
