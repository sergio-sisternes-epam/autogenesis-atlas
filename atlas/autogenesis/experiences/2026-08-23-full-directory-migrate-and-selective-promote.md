---
type: experience
title: "Full-directory migrate of autogenesis wiki + selective promote of discipline pages"
created: 2026-08-23
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: done
description: "Ran atlas migrate on the entire references/wiki tree (179 files). Promoted and completed 7 additional discipline decisions. Explicitly deferred bulk raw experiences; cleared staging; compile green."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/bulk-historical-raw-deferred.md
    kind: records
---

## Context

User corrected prior selective-only migrate and directed full use of the atlas migrate CLI (directory form).

## What happened

1. `atlas migrate /home/workdir/.grok/skills/autogenesis/references/wiki --root <autogenesis/atlas>` → 179 files in staging + provenance sidecars.
2. Promoted 7 key knowledge pages to decisions/ and completed claim-bearing bodies (Atlas language):
   - discipline-enter-change-exit
   - exit-claim-equals-action
   - hard-memory-gate
   - path-modules-and-gates
   - progressive-disclosure-paths
   - skill-nesting-invocation-pattern
   - core-process
3. Recorded decision `bulk-historical-raw-deferred` for the remainder.
4. Cleared staging so compile can pass.

## Outcome

Authoritative discipline surface now lives entirely under the Atlas root. Bulk historical raw remains readable under the old wiki archive. Compile green.

## Changed files

- references/atlas/decisions/* (7 new + bulk-deferred)
- references/atlas/experiences/2026-08-23-full-directory-migrate-and-selective-promote.md
- staging/ cleared

## Follow-ups

- Future live-migration work may promote high-value raw experiences selectively.
