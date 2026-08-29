---
type: experience
title: "2026-08-16 Autogenesis run: corpus expansion for new skill apm from microsoft/apm docs"
created: 2026-08-16
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: unverified
description: "User requested creation of new skill apm via autogenesis; first step ingest all microsoft/apm documentation with git provenance into the target skill's own wiki, grouped by large topics, contained in module apm."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-16-apm-skill-corpus-expansion`.

## What happened

## What was novel

- Target skill did not yet exist (only apm-install sibling).
- User framed as "autogenesis skill we need to create a new skill called apm" + "for starters, ingest all the documentation in microsoft/apm".
- Explicit requirement: keep provenance on git sources in frontmatter (resource + git_commit + git_path + source_repo) for future upgrades.
- Desired shape: ingested information contained in a module called apm, files grouped by large topics.

## What was done

1. Initialised target skill skeleton at `/home/workdir/.grok/skills/apm/references/wiki/` from okf-wiki store-skeleton.
2. Shallow-cloned microsoft/apm @ 8993dcc6fd7171ef3881a9021a7f25b9439e1a29.
3. Captured 128 documentation files (122 under docs/src/content/docs + 6 root) into `raw/articles/microsoft-apm/` preserving topic hierarchy, renaming index.md → index-page.md to satisfy reserved-name rule.
4. Frontmatter on every raw file includes the required git provenance fields.
5. Partial dual-axis: wrote 5 substantive core concept pages + 1 topic-overview (not inventory digests). Validate ok; coverage intentionally incomplete for the long tail.
6. Updated target index.md and log.md. No SKILL.md body yet (implement forbidden until plan approved).

## Outcome

Corpus expansion step of the autogenesis loop is complete and durable in the *target* skill's wiki. Ready for genesis design of the apm skill itself, self think-challenge, composition-safety note, and persisted plan for user approval.

## Notes / risks observed

- Previous pointer-memory failure on a similar APM ingest (recorded in okf-wiki) was deliberately avoided by writing real concept content instead of file inventories.
- Full topic-level extraction + promote-to-module `apm` remains open work; do not claim ingest complete.
- Creating a skill from external docs (not from an existing skillset's experience store) sits at the edge of autogenesis's stated "grow an existing skillset" charter; treated as allowed because the user invoked autogenesis and the write scope stayed inside the new target.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
