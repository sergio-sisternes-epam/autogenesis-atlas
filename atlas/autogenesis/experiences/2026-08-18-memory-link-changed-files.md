---
type: experience
title: "2026-08-18 Implement: memories must link back to changed files"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Hardened templates, Exit checklist and knowledge rule so every future remember experience systematically lists the product files it touched."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-memory-link-changed-files`.

## What happened

## What the user asked
- After reviewing the previous implement experience, noted that changed files were listed as plain text but not strongly linked.
- Asked how we can incorporate this feedback so memories systematically link back to the concrete changes.
- Explicitly “Approved” the A+B+C package (templates + Exit gate + knowledge rule).

## What was done
Implemented the approved plan `artifacts/autogenesis-plans/2026-08-18-memory-link-changed-files.md`.

## Changed files
- `artifacts/autogenesis-plans/2026-08-18-memory-link-changed-files.md` (created)
- `references/run-record-template.md` (updated – mandatory Changed files section)
- `SKILL.md` (updated – Exit activation checklist step 5)
- `references/paths/implement.md` (updated – Exit step requires Changed files list)
- `references/wiki/knowledge/memory-link-changed-files.md` (created)
- `references/wiki/knowledge/vocabulary-lineage-remember-ingest.md` (updated – new normative rule 4)
- `references/wiki/index.md` (will be updated)
- `references/wiki/raw/experiences/2026-08-18-memory-link-changed-files.md` (this file)

## Pinned decisions
- A + B + C only (option D deferred).
- Relative paths for non-wiki files; `[[wikilinks]]` for wiki pages.
- Missing Changed-files section on a mutating Run → incomplete G8.
- Rule is queryable via the new knowledge page.

## Outcome
Future Autogenesis remember experiences (especially implement) are now required to link back to every product file they touched. The learning is durable in both process (templates + gates) and knowledge.

Related: [[knowledge/memory-link-changed-files]], [[knowledge/vocabulary-lineage-remember-ingest]], [[knowledge/hard-memory-gate]].

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
