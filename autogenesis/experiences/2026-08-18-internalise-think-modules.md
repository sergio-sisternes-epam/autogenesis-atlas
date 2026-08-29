---
type: experience
title: "2026-08-18 Implement: internalise think-* as modules"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Imported all three root think skills as progressive-disclosure modules under references/modules/; updated design path and registry; root think-* left intact."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-internalise-think-modules`.

## What happened

## What the user asked
- Concern that think dependencies were external.
- Wanted to internalise copies so they live and evolve inside autogenesis.
- Keep root-level versions (used for other purposes).
- Check okf-wiki first (it does not depend on them).
- Then: bring each think-* as a module for a flatter skill structure; import all three in case autogenesis needs ramble or grill on user request.
- Liked the `modules` idea; confirmed no existing modules inside autogenesis.
- Explicit “Approved”.

## What we did
1. Persisted plan: `artifacts/autogenesis-plans/2026-08-18-internalise-think-modules.md`.
2. Created first `references/modules/` directory.
3. Wrote three internal modules (snapshot of root bodies + nesting adaptations + provenance):
   - `references/modules/think-challenge.md`
   - `references/modules/think-grill.md`
   - `references/modules/think-ramble.md`
4. Updated `references/paths/design.md` step 2 to load the internal module by relative path (no root-skill name lookup).
5. Updated root `SKILL.md`:
   - design registry stub and CHANGE table
   - new “Internal think modules” section so on-request triggers resolve to the modules while an Autogenesis Run is active
6. Updated supporting knowledge / templates:
   - `knowledge/design-path-sequence.md`
   - `knowledge/core-process.md`
   - `challenge-success-criteria.md`
   - `paths/reflect-challenge.md`
7. Root `think-*` skills were **not** modified or deleted.

## Pinned decisions (from approved plan)
- Modules live under `references/modules/` (flatter, parallel to paths/).
- All three imported even though only challenge is currently required by design.
- Modules are progressive-disclosure only; never catalog skills.
- Future evolution of the internal copies happens only via Autogenesis Runs on subject=autogenesis.

## Outcome
Design path and on-request think verbs now use internal modules. External coupling removed for thinking ops. Structure is flatter. Lineage recorded here.

Related: [[knowledge/design-path-sequence]], [[knowledge/core-process]], [[knowledge/progressive-disclosure-paths]], plan at artifacts/autogenesis-plans/2026-08-18-internalise-think-modules.md.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
