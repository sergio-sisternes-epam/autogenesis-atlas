---
type: decision
title: "Memory substrate for Autogenesis is Atlas (not okf-wiki)"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Authoritative process memory for the autogenesis skill (and subjects under it) uses Atlas paths only. The former okf-wiki store under references/wiki/ is superseded for new writes."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/lineage-and-remember-via-atlas.md
    kind: related
  - path: autogenesis/decisions/hard-memory-gate.md
    kind: related
  - path: autogenesis/decisions/exit-claim-equals-action.md
    kind: related
  - path: autogenesis/decisions/memory-link-changed-files.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
    kind: related
---

## Decision

**Atlas is the sole process-memory substrate for Autogenesis.**

- All new experiences, decisions, lessons, recipes and work hubs for this skill are written via Atlas `remember` / `work` paths into `references/atlas/`.
- Query uses Atlas `query` path (`atlas search`).
- okf-wiki is **not** activated for memory ops of this skill. The old `references/wiki/` remains as read-only historical archive until full live migration (tracked under atlas-bm25-and-live-migration-v1).

This decision supersedes the former knowledge page `memory-via-okf-wiki.md` (and the rule that “okf-wiki is the only ingestion authority”).

## Rationale


## Alternatives considered

- Keep dual-home (okf-wiki + Atlas) — rejected (drift, double effort).
- Disable the old wiki immediately and force bulk rewrite of 170+ pages — rejected (scope explosion; bulk historical migration is separate deferred work).
- Leave memory authority unspecified — rejected (breaks G8 / lineage rules).

## Consequences

- SKILL.md, workflow-discipline.md and all path modules that previously said “activate okf-wiki for remember/ingest” must be updated to load Atlas paths instead.
- New Runs under Autogenesis write only to the Atlas root.
- Old `[[raw/…]]` and knowledge pages remain readable for lineage but are not the write target.
- Compile of this Atlas root must stay green; staging never answers.
