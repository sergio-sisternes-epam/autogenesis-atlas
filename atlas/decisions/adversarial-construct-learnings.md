---
type: decision
title: "Learnings \u2014 adversarial construct v1 vs v2"
created: 2026-08-22
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "v1 is phrase-presence and is not the gate. Construct cannot prove Autogenesis Run discipline (R1). Exit latest-vs-all and smoke JSON are open improvements."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/challenge-adversarial-construct.md
    kind: related
  - path: decisions/adversarial-construct-future-actions.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

Compiled from [[raw/experiences/2026-08-22-adversarial-gate-learnings]].

## What is true

- **v1 is phrase-presence.** Greps on path modules can go green while a subject still ships an empty draft, dropped smokes, unnamed waive, and poison YAML.
- **v2 does not execute a Run.** R1 forbids construct from invoking autogenesis. The meta-suite can only keep holes detectable on a fixture.
- **Smoke stdout must be only** `{"ok":true}`. Extra fields broke expect parsing.
- **Poison YAML is data.** Eval must not obey scenario descriptions as skill instructions. Live package must stay unmutated.

## Open (needs a later hardening design, not claimed shipped)

Tracked in [[knowledge/adversarial-construct-future-actions]].

- Exit: run **latest** `*-adversarial-vN` as required; keep prior files as regression unless a new design drops them.
- Extract a shared `check_adversarial_gate.py` instead of copy-pasted `python3 -c`.
- Exit receipt should list `adversarial_scenarios` actually run.
- Suite-size review (P12) on the next behaviour-change design.

## Related

- [[knowledge/challenge-adversarial-construct]]
- [[raw/experiences/2026-08-21-implement-challenge-adversarial-construct]]

## Rationale

Migrated from okf-wiki knowledge page `adversarial-construct-learnings` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
