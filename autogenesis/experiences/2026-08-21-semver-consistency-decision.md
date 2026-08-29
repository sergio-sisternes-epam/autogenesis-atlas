---
type: experience
title: "Decision: consistent semver for all skills"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "IMPORTANT process rule. All skills use MAJOR.MINOR.PATCH only. Date stamps retired. Applied to okf-wiki, agent-brain, autogenesis, okf in the wire/handoff arc."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-semver-consistency-decision`.

## What happened

## Rule (important)

**All skills use semantic versioning only:** `MAJOR.MINOR.PATCH`.

- No date-based version stamps (e.g. `2026-08-18.1` is retired).
- Bump when behaviour or contracts ship (not only docs).
- Keep version field in SKILL.md frontmatter.

## Applied (2026-08-21)

| Skill | Version |
|-------|---------|
| okf-wiki | 0.2.0 |
| agent-brain | 0.2.5 |
| autogenesis | 0.2.0 |
| okf | 0.1.0 |
| knowledge-crawl | 0.1.0 (already) |
| terraform | 0.1.0 (already) |

## Why

Mixed schemes (date vs semver) made it hard to see what shipped. One scheme across the skillset.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
