---
type: experience
title: "PINNED: Three-axis composition model (content \u00b7 store \u00b7 capability)"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "IMPORTANT. Content, store composition, and capability are orthogonal. Package may require more-stable packages; knowledge mesh rules depend on scenario; write isolation preserved."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-three-axis-composition-pinned`.

## What happened

## Axes (orthogonal)

| Axis | Name | Concern |
|------|------|---------|
| **A** | **Content** | knowledge (judgment) ← sources — raw (evidence); local wire + confidence |
| **B** | **Store composition** | project · package · mesh (read-only virtual resolve; hops; receipts) |
| **C** | **Capability** | skill **requires** skill via versioned contracts/paths (manifest); acyclic; depend toward stability |

Do not collapse these into one L*/edge type.

## Hardenings (think-challenge, all agreed)

### H-C1 — Not all package dependencies are equal
- **Capability/contract** deps may live in **package** manifests (SKILL.md / requires).
- **Knowledge mesh** edges are scenario-scoped (see H-C3).
- **Runtime wiring** (which stores in session, hop policy) is project/composition-root.

### H-C2 — Behaviour composition ≠ knowledge coupling
- Composable behaviour = published **paths/contracts** + capability requires.
- Knowledge mesh = navigation among **curated judgments**.
- OKF format → okf-wiki ops → agent-brain use is **interface composition**, not domain knowledge tangle.

### H-C3 — Scenario determines knowledge dependency
- Strict default: domain skill ↛ durable mesh into another domain skill’s package knowledge.
- **When a skill carries a capability dependency on another skill, it may also carry the corresponding knowledge dependency** (entry points / procedures needed to use that capability).
- Scenario decides:
  - **Platform stack** (okf → okf-wiki → agent-brain): capability + supporting knowledge links allowed in package.
  - **Domain ↔ domain** (e.g. terraform ↔ unrelated skill): prefer **project** mesh edges.
  - **Project workspace**: always may own mesh edges among selected packages.

### H-C4 — Keep axes explicit
- Content ≠ store view ≠ capability graph.

### H-C5 — Assembler still required
- Stable lower packages export contracts.
- Higher packages require those contracts.
- **Project** selects domain skills and optional knowledge entry paths for the workspace.

## Package vs project (summary)

```text
PACKAGE
  - own knowledge + raw
  - manifest requires: more-stable packages (capability)
  - may include knowledge entry links for those required capabilities (H-C3)
  - exports paths/contracts
  - no cycles; depend toward stability (SDP/ADP)

PROJECT (composition root)
  - selects packages + versions
  - owns workspace mesh edges (especially domain↔domain)
  - resolve: project → package → mesh under hop policy
  - write-root for project use

PLATFORM
  - layered capability DAG (okf → okf-wiki → agent-brain / autogenesis)
```

## Write isolation (unchanged)
- Writes only to active write-root.
- Mesh follow ≠ write into peer package.
- Promotion still D4 (train report / PR / human approval).

## Implications for mesh tasks
1. **Reverse index** — primarily over **project** composition + optional host catalog; package reverse only for declared capability/knowledge deps of that package.
2. **Project resolve roots** — first-class; package resolve remains for skill-train context.

## Related
- composition-axis-all-pins-and-backlog
- mesh-composition-axis-design plan
- package promotion D4

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
