---
type: experience
title: "Think-challenge: Panel Review severity format (Blocker / Recommended / NIT)"
created: 2026-08-22
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Pinned: mandate named trio is too specific; omit severity too weak; require abstract graded weights (must/should/optional); Blocker\u2013Recommended\u2013NIT only as example vocabulary. Advisory regime preserved."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/challenge-adversarial-construct.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-22-challenge-panel-review-severity-format`.

## What happened

## Question
Should the Panel Review pattern include recommendations format Blocker / Recommended / NIT as reference, or is that too specific?

## Counters pinned

1. **Graded severity solves a real force** — blocking vs non-blocking (and optional polish) reduces ambiguity; unlabeled findings are often read as mandatory.
2. **Exact labels are a concretion** — Blocker/Recommended/NIT is one dialect among many (Conventional Comments, Critical/Error/Info, etc.). Mandating those names locks the pattern to one culture.
3. **Severity interacts with advisory regime** — calling items “Blocker” can reintroduce social/merge-gate pressure the advisory stance was meant to avoid.
4. **Omitting priority entirely is too weak** — synthesizer and personas need a weight dimension or the single comment becomes an unprioritized pile.

## Decision

| Option | Verdict |
|--------|---------|
| Mandate “Blocker / Recommended / NIT” by name | Too specific |
| Omit any severity / priority | Too weak |
| **Require abstract graded finding weights; cite named schemes only as examples** | **Adopted** |

Concrete rule for the pattern:
- Each finding carries a **weight**: must-address before ship / should-address / optional polish (adopter may rename).
- Example vocabularies may be listed as reference only: Blocker / Recommended / NIT; Conventional Comments; Critical / High / Info.
- Weights inform the ship_recommendation stance; they do **not** auto-apply gate labels unless the deployment explicitly leaves pure advisory mode.

## Related
- Panel Review draft (to be updated with this rule)
- [[raw/experiences/2026-08-22-extract-triage-panel-draft]]
- [[knowledge/concept-patterns-module]]

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
