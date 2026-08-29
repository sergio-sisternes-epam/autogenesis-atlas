---
type: experience
title: "Ontology type migration applied (autogenesis wiki)"
created: 2026-08-22
work_id: okf-wiki-ontology-type-v1
status: raw
description: "Ran type-inventory + type-normalise --apply --force for new type vocabulary, origin and sensitivity under work_id okf-wiki-ontology-type-v1"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: work/okf-wiki-ontology-type-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/challenge-adversarial-construct.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-22-ontology-type-migrate`.

## What happened

User requested migration of skills (okf, okf-wiki, autogenesis, agent-brain, construct) to the new wiki ontology.

For this skill's process memory at references/wiki:

1. type-inventory produced report (scanned 151, high 125, low 23, policy 2, unchanged 1).
2. type-normalise --apply --force wrote 125 pages; 2 policy proposals blocked (low confidence keyword signals on aware-runtime experiences).
3. validate: critical empty, ok.

This experience records the event for lineage. Ontology design and migrate-type tooling live under okf-wiki work_ids.

Gates: post-migration validate passed.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
