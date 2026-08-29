---
type: decision
title: "Design plans persist in the subject Atlas only"
created: 2026-08-23
status: accepted
work_id: autogenesis-plan-home-subject-atlas-v1
description: "Primary plan home is the subject skill Atlas. If missing, inform user and offer initiate Atlas; if okf-wiki exists, also offer migration. No silent artifacts/ fallback."
relates_to:
  - path: work/autogenesis-plan-home-subject-atlas-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: follows
  - path: decisions/discipline-enter-change-exit.md
    kind: related
---

## Decision

1. **Plan home** = subject Atlas (`<subject>/references/atlas/`), as a claim-bearing page (convention: `experiences/YYYY-MM-DD-design-plan-<work_id>.md`).
2. **`plan_path`** in receipts and work hubs is **Atlas-relative**.
3. **If no Atlas:** stop, inform the user, offer **initiate Atlas** (and **migrate okf-wiki → Atlas** when `references/wiki/` exists), or abort.
4. **`artifacts/autogenesis-plans/`** is not the primary plan home (optional provenance copy only).

## Rationale

Plans are process memory. Storing them outside the subject Atlas splits the graph and reintroduces the dual-home problem already rejected for experiences/decisions.

## Alternatives considered

- Keep artifacts/ as primary with Atlas pointer — rejected (split graph).
- Auto-create Atlas without asking — rejected (user must consent to store bootstrap/migration).

## Consequences

design, initialise, and reevaluate paths resolve subject Atlas before plan persist. workflow-discipline Subject Atlas resolution table is normative.
