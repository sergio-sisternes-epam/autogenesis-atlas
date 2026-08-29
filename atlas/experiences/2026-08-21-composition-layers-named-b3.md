---
type: experience
title: "PINNED: Composition layers use names only (B3)"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "IMPORTANT. No L1/L2/L3 digits for composition. Layers are project \u00b7 package \u00b7 mesh. Avoids foundation-vs-specific confusion."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-composition-layers-named-b3`.

## What happened

## Decision

Composition axis uses **named layers only**:

| Name | Role |
|------|------|
| **project** | Most-specific root for the active context (often `.agents/…` overlay; or skill `references/` when training the skill itself) |
| **package** | Shipped agent/skill wiki under `references/` |
| **mesh** | Explicit inter-store edges between brains/skills |

**Do not** use L1/L2/L3 digits for composition in formal contracts, pins, or path modules.

## Why

“L1” is widely read as foundation/base; our **project** layer is *most specific* (overlay upper). Named layers remove that ambiguity and stay orthogonal to the content axis (knowledge vs raw).

## Interaction with Axis B pin

Update mental model:

```text
read:   project → package → mesh (hop-limited by think effort)
write:  project only (context-defined write-root)
cross-store edges: knowledge → knowledge only
```

Prior “L1/L2/L3” wording in Axis B pins means **project / package / mesh** respectively.

## Related

- [[raw/experiences/2026-08-21-axis-b-virtual-resolve-pinned]]

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
