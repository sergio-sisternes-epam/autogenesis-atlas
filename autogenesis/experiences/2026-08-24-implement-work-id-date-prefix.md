---
type: experience
title: "Implement dated work_id convention (YYYY-MM-DD prefix)"
description: "Applied approved hardening: new work_ids are YYYY-MM-DD-<slug> (with optional external_id); no backward renames."
created: 2026-08-24
work_id: 2026-08-24-work-id-date-prefix
status: done
tags: [autogenesis, implement, work_id, naming]
origin: internal
sensitivity: internal
implements: 2026-08-24-work-id-date-prefix
closes: 2026-08-24-work-id-date-prefix
plan_path: autogenesis/plans/2026-08-24-work-id-date-prefix.md
construct_eval: deferred
relates_to:
  - path: autogenesis/plans/2026-08-24-work-id-date-prefix.md
    kind: implements
  - path: autogenesis/work/2026-08-24-work-id-date-prefix.md
    kind: implements
  - path: autogenesis/experiences/2026-08-24-design-work-id-date-prefix.md
    kind: follows
---

## Context

User requested work_id and plan names include yyyy-mm-dd at the beginning for chronological ordering, then refined to embed external_id in the slug when specified. Design approved; implement in same session.

## What happened

- Updated `references/modules/workflow-discipline.md` work_id lineage section with dated format, external_id rule, and no-backward-rename rule.
- Updated `references/paths/design.md` step 0 (Assign work_id).
- Updated root `SKILL.md` Plans bullet with format note.
- Persisted plan, work hub, and this experience under the new naming convention.
- No existing plan or work files renamed.

## Outcome

New Autogenesis work will sort chronologically alongside experiences. Historical work remains stable.

## Changed files

- references/modules/workflow-discipline.md
- references/paths/design.md
- SKILL.md
- references/atlas/autogenesis/plans/2026-08-24-work-id-date-prefix.md
- references/atlas/autogenesis/work/2026-08-24-work-id-date-prefix.md
- references/atlas/autogenesis/experiences/2026-08-24-implement-work-id-date-prefix.md
- references/atlas/autogenesis/plans/index.md (stub)
- references/atlas/autogenesis/work/index.md (stub)
- references/atlas/autogenesis/experiences/index.md (stub)
- references/atlas/log.md

## Related

- Plan and work hub for this work_id

## Follow-ups

None.
