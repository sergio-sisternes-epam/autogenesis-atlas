---
type: decision
title: "Decision: Panel Review uses abstract finding weights, not a mandated label trio"
created: 2026-08-22
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Require must-address / should-address / optional (or equivalent). Blocker / Recommended / NIT only as example vocabulary. Preserve advisory regime."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

Pinned after think-challenge on whether to include Blocker / Recommended / NIT in the Panel Review pattern.

## Rule

1. **Require** a graded finding weight on structured persona findings (abstract): e.g. must-address before ship · should-address · optional polish. Adopters may choose local names.
2. **Do not mandate** the strings “Blocker”, “Recommended”, or “NIT” in the pattern body.
3. **May list** those names (and Conventional Comments, Critical/High/Info, etc.) only as **example vocabularies**.
4. Weights inform the synthesizer’s ship_recommendation stance. They do **not** auto-apply merge-gate labels unless the deployment explicitly exits pure advisory mode.

## Rationale (short)

- Priority is a real force (unlabeled findings read as mandatory).
- Named trios are culture-specific concretions.
- “Blocker” language can undermine the advisory-not-gate invariant.
