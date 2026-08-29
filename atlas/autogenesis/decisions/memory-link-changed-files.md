---
type: decision
title: "Memories must link back to changed files"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Migrated knowledge: Memories must link back to changed files"
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
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Rule (normative from 2026-08-18)

Every Autogenesis `Atlas remember` experience that is produced by a Run which **created or edited product files** must contain a structured section:

```markdown
## Changed files
- relative/path/from/skill/root.md (created | updated)
- [[knowledge/some-page]] (created | updated)
```

- Use relative paths for files that live outside the wiki store (SKILL.md, path modules, templates, modules, etc.).
- Use `[[wikilinks]]` for pages that live inside the subject Atlas.
- The list must be complete for the scope of the Run. Partial lists are treated as incomplete Exit (G8).

## Why

Without this link the memory graph knows *that* work happened but cannot reliably navigate back to the concrete artefacts. Later design, review, or query runs lose provenance.

## Where enforced

- `references/run-record-template.md` — mandatory section in the body template
- Root `SKILL.md` Exit activation checklist (step 5)
- `references/paths/implement.md` Exit step
- This knowledge page (queryable)

## Non-goals

- True `[[wikilinks]]` to files outside the wiki store (impossible under OKF conventions)
- Retro-fitting historical experiences
- Changing Atlas (formerly okf-wiki)’s general remember/ingest modules
