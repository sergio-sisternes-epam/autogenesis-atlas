---
type: experience
title: "Implement: switch Autogenesis discipline to Atlas-only memory"
created: 2026-08-23
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: done
description: "Hardening implement of the reevaluate proposals. SKILL.md, workflow-discipline.md and core path modules now reference only Atlas."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: experiences/2026-08-23-reevaluate-memory-substrate-atlas.md
    kind: follows
  - path: decisions/memory-substrate-is-atlas.md
    kind: records
---

## Context

User-directed migration complete for content; discipline review produced concrete proposals; hardening design plan approved by explicit user language.

## What happened

- Updated SKILL.md Experience source, progressive disclosure, failure modes, version → 0.3.2.
- Rewrote workflow-discipline hard boundaries, Exit checklist, path receipt, gate map G2/G6/G8, R4, work-node locations.
- Updated design, implement, reevaluate, research, initialise, learn-skill, review-package path modules (Exit + subject_scope + descriptions).
- Left old references/wiki/ as read-only historical archive.

## Outcome

Discipline now uses only Atlas for process memory. Compile of the new Atlas root remains green.

## Changed files

- SKILL.md
- references/modules/workflow-discipline.md
- references/paths/design.md
- references/paths/implement.md
- references/paths/reevaluate.md
- references/paths/research.md
- references/paths/initialise.md
- references/paths/learn-skill.md
- references/paths/review-package.md
- references/atlas/** (new store)
- artifacts/autogenesis-plans/2026-08-23-autogenesis-memory-substrate-atlas-hardening.md

## Follow-ups

- Residual path-module copy that still contains the old vocabulary strings can be cleaned in a later hardening pass.
- Full bulk migration of 139 raw experiences remains deferred.
