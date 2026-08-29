---
type: plan
title: "work_id and plan names start with YYYY-MM-DD"
created: 2026-08-24
work_id: 2026-08-24-work-id-date-prefix
status: done
change_class: hardening
subject: autogenesis
description: "Require new work_id values (and thus plan/work filenames) to start with YYYY-MM-DD for chronological sort; embed external_id in slug when present; no backward renames."
origin: internal
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-08-24-work-id-date-prefix.md
    kind: implements
---

## Intent + scope

Align Autogenesis plan/work naming with experience naming so directories sort by time. New work only; historical files untouched.

## Non-goals

- Renaming any existing work_id, plan, or work hub
- Changing experience filename rules
- Changing status vocabulary or relates_to kinds

## Pins

1. New work_id: `YYYY-MM-DD-<kebab-slug>`
2. With external id: `YYYY-MM-DD-<external_id>-<kebab-slug>`
3. Plan/work paths use `<work_id>.md`
4. No backward renames
5. Date = plan creation date

## Genesis Artifacts

### Intent + scope + non-goals
(see above)

### Acceptance
- workflow-discipline.md states the dated format and no-rename rule
- design.md assign-work_id step states the same
- SKILL.md notes the format
- This plan uses the new convention
- No historical files renamed

## Residual risks

Mixed sort order until old work ages out — accepted.

## Stop for approval

Approved by user 2026-08-24; implement applied in same Run.
