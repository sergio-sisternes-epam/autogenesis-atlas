---
type: experience
title: "Publish and review the Autogenesis Atlas storage migration"
created: 2026-09-05
work_id: 2026-09-05-atlas-storage-semantics
status: reviewed
description: "Session record covering canonical-store publication, Autogenesis PR creation, review fixes, and final validation under the new storage discipline."
tags:
  - atlas-storage
  - pull-request
  - review
  - validation
origin: internal
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-09-05-atlas-storage-semantics.md
    kind: implements
  - path: autogenesis/plans/2026-09-05-atlas-storage-semantics.md
    kind: implements
  - path: autogenesis/experiences/2026-09-05-implement-atlas-storage-semantics.md
    kind: follows
  - path: autogenesis/decisions/policy-lookup-uses-owner-atlas.md
    kind: records
---

## Context

The storage migration had reached a compile-green local implementation, but
the canonical store commit and parent source branch still needed publication,
review, and an explicit record of the new resolver discipline.

## What happened

- The canonical `autogenesis-atlas` changes were committed locally through
  `f41bbdc` and published on non-main branch
  `sergio-sisternes-epam-atlas-storage-semantics`.
- The Autogenesis migration was committed as `aaafd92`, pushed, and opened as
  PR #2.
- Review identified two contract gaps:
  1. the nesting audit resolved the audited subject's Atlas instead of the
     Autogenesis policy owner's Atlas;
  2. `atlas-migrate` demanded explicit identity instead of using the shared
     explicit-or-exactly-one fail-closed rule.
- Commit `2ff4a72` corrected both gaps, added a deterministic identity-selection
  smoke, and resolved both review threads.
- Scenario validation exposed a shell-specific hazard: Markdown backticks
  inside double-quoted `python3 -c` programs trigger command substitution.
  The smokes now single-quote those programs and require clean stderr.
- The happy-path compile smoke executes `atlas resolve` and compiles the
  returned root rather than reconstructing `.atlas/<id>`.

## Changed files

- `autogenesis/decisions/policy-lookup-uses-owner-atlas.md`
- `autogenesis/decisions/index.md`
- `autogenesis/experiences/2026-09-05-atlas-storage-migration-publication-and-review.md`
- `autogenesis/experiences/index.md`
- `autogenesis/work/2026-09-05-atlas-storage-semantics.md`

## Outcome

- 22 deterministic happy-path and adversarial smokes pass with clean stderr.
- The canonical Atlas compiles with zero critical findings, zero warnings, and
  empty staging.
- Autogenesis PR #2 is review-clean and mergeable, but remains unmerged.
- No tag, release, global APM update, settings mutation, or Atlas/Discuss source
  change occurred.
- The canonical-store branch still requires its own separately approved PR and
  merge before Autogenesis PR #2 should merge.

## Related

- Autogenesis PR #2:
  https://github.com/sergio-sisternes-epam/autogenesis/pull/2
- Implementation experience:
  `autogenesis/experiences/2026-09-05-implement-atlas-storage-semantics.md`

## Follow-ups

- Obtain explicit approval to open and land the canonical-store PR.
- After both repositories land and v0.4.0 is released, obtain separate approval
  for the global APM dry-run and update.
