---
type: experience
title: "Design: work_id and plan names start with YYYY-MM-DD"
description: "Formal design for dated work_id convention; pins accepted then refined to embed external_id in slug when present; approved for implement."
created: 2026-08-24
work_id: 2026-08-24-work-id-date-prefix
status: done
tags: [autogenesis, design, work_id, naming]
origin: internal
sensitivity: internal
relates_to:
  - path: autogenesis/plans/2026-08-24-work-id-date-prefix.md
    kind: implements
  - path: autogenesis/work/2026-08-24-work-id-date-prefix.md
    kind: implements
  - path: autogenesis/experiences/2026-08-24-implement-work-id-date-prefix.md
    kind: related
---

## Context

User asked that Autogenesis work_id and plan names include yyyy-mm-dd at the beginning so they order by time like experiences. No backward renames. Later refined: if an external_id is specified, place it in the slug after the date.

## What happened

- Change-class: hardening.
- Proposed format `YYYY-MM-DD-<kebab-slug>`; with external id `YYYY-MM-DD-<external_id>-<kebab-slug>`.
- Pins: date first, optional external_id, descriptive slug required, no renames of historical work.
- Plan persisted at `autogenesis/plans/2026-08-24-work-id-date-prefix.md` under the new convention itself.
- User approved; implement followed in the same session.

## Outcome

Design accepted. Implement experience records the file edits.

## Related

- Plan, work hub, and implement experience for `2026-08-24-work-id-date-prefix`

## Follow-ups

None — implement completed.
