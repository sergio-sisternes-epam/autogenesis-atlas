---
type: decision
title: "Block discussion \u2192 implement short-circuit"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Migrated knowledge: Block discussion \u2192 implement short-circuit"
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/core-process.md
    kind: related
  - path: autogenesis/decisions/path-modules-and-gates.md
    kind: related
  - path: autogenesis/decisions/progressive-disclosure-paths.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Rule (normative from 2026-08-18)

Discussion mode **never** proceeds directly to implement.

The only legal transition is:

```
discussion  →  formal design (mode: run, path: design)
            →  persisted + challenged plan (genesis → internal think-challenge → pin → C1–C5)
            →  explicit user approval of that plan
            →  implement
```

Any attempt to jump the gate (e.g. user says “Approved / implement / just do it” while still in discussion or while no formal design plan exists) is **refused**. The agent must re-issue an Enter card for `mode: run, path: design` and complete the full design sequence before implement becomes legal.

## Rationale

Past Runs short-circuited discussion sketches straight into implement after a casual “Approved”. That skipped the grounded challenge, autonomous pin, and C1–C5 criteria. The short-circuit is now an explicit incomplete condition (G4).

## Enforcement points

- Root `SKILL.md` Enter rules (rule 4) and Hard boundaries table
- `references/paths/implement.md` “When (Change)”
- This knowledge page (queryable)

## Non-goals of this rule

- No mandatory think-challenge inside pure discussion
- No emergency-override flag (deferred; can be designed later if the absolute block proves too rigid)
- No retro-fitting of historical experiences that used the short-circuit
