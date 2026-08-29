---
type: experience
title: "Discussion captured: skill wiki vs project overlay under agent-brain"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Autogenesis lineage pointer to the modular-brain / overlay model discussed 2026-08-21. Skill package memory stays in references/; overlays under .agents/agent-brain/<id>/; promotion via recurrence + Git PR."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-skill-wiki-vs-project-overlay-discussion`.

## What happened

Full locked decisions live primarily in agent-brain:

`agent-brain/references/wiki/raw/experiences/2026-08-21-skill-wiki-vs-project-overlay-discussion.md`

## Why Autogenesis cares
- Designs/reviews skills that own `references/wiki`.
- Must not emit test plans or Train guidance that dump domain corpora into the **skill** wiki when the intent is project training.
- Promotion into skill memory should align with human/Git approval, not only in-chat yes.
- agent-brain is the designated host of the modular overlay tree (`.agents/agent-brain/<id>/`).

## Formal plan
See `artifacts/autogenesis-plans/agent-brain-skill-vs-project-overlay-2026-08-21.md` (stops for approval).

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
