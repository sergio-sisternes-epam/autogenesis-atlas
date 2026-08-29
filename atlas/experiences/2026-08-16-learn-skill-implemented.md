---
type: experience
title: "learn-skill capability implemented via Autogenesis loop"
created: 2026-08-16
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Migrated experience: learn-skill capability implemented via Autogenesis loop"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/challenge-adversarial-construct.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-16-learn-skill-implemented`.

## What happened

## Lineage
- Source idea: user request to formalise skill-to-skill wiki connections + progressive disclosure
- Design packet: `artifacts/autogenesis-plans/learn-skill-capability-2026-08-16.md`
- Challenge: self think-challenge (noisy links, write scope, copy risk, cost, wiring back-door)
- Composition-safety note: clean
- Version produced: 0.1.0
- Implementation: inline section in `autogenesis/SKILL.md` + first concrete peer-link (okf-wiki)

## Reflection
**What worked**
- Treating the idea as an Autogenesis target (instead of only discussing it) produced a concrete, bounded capability quickly.
- Keeping it inline (not a new root skill) matched the small size and tight coupling to ownership rules.
- Immediately exercising it to link autogenesis → okf-wiki made the distributed-net real.

**What to improve**
- Reciprocal links (okf-wiki learning about autogenesis) should be a separate explicit learn-skill invocation from the other side, not done automatically.
- Template for the peer-link page can be tightened further.
- Later: optional promotion path from `status: unverified` peer-links into more stable knowledge pages.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
