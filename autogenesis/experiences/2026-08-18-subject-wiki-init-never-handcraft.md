---
type: experience
title: "Implement: canonical subject-wiki init via okf-wiki (never hand-craft)"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Applied approved design plan \u2014 generalised wiki-init + Exit hard rule"
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-subject-wiki-init-never-handcraft`.

## What happened

## What the operator asked

After skill-feedback and a formal design path, the operator approved the plan and said “Plan approved. Implement”.

## Approved scope (no creep)

From `artifacts/autogenesis-plans/2026-08-18-autogenesis-subject-wiki-init.md`:

1. Generalise `okf-wiki/references/modules/wiki-init.md` to accept an arbitrary root (default remains session store).
2. Update Autogenesis Exit checklist (`workflow-discipline.md`) and `wiki-lineage-autogenesis` with the missing-root branch + hard rule “never hand-craft”.
3. Version both packages to 2026-08-18.1.
4. No other files.

## What was done

- `wiki-init` now accepts optional root; process rewritten cleanly; SCHEMA.md is the preferred existence check.
- `workflow-discipline.md` Exit activation checklist now contains the cheap SCHEMA.md check and the mandatory “if missing → substrate → wiki-init” branch, plus the hard rule.
- `wiki-lineage-autogenesis.md` updated with the same pre-step and vocabulary entry.
- Version identity set on both skill roots and the changed modules.
- No auto-wire; no peer content copy beyond the approved scope.

## Changed files

- okf-wiki/references/modules/wiki-init.md
- okf-wiki/references/modules/wiki-lineage-autogenesis.md
- okf-wiki/SKILL.md
- autogenesis/references/modules/workflow-discipline.md
- autogenesis/SKILL.md
- artifacts/autogenesis-plans/2026-08-18-autogenesis-subject-wiki-init.md

## Ingest deferral

No knowledge pages were created or materially updated in this Run. Ingest deferred: process lineage only; durable rule already captured in the modules and this experience.

## Related

- [[raw/experiences/2026-08-18-medium-implement-nesting-and-paths]] (the incident that triggered the feedback)
- skill-feedback report 2026-08-18
- design plan 2026-08-18-autogenesis-subject-wiki-init

## Gates

G4 (explicit approval) · G5 (scope match + version) · G6 / G8 (this lineage)

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
