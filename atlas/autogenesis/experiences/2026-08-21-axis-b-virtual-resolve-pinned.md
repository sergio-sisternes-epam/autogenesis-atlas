---
type: experience
title: "PINNED: Axis B virtual resolve filesystem (Counter A + A.1\u2013A.4)"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "IMPORTANT. Composition axis is a read-only virtual resolve view, not a writable union disk. Think-effort hop limits; context-dependent L1; cross-store links knowledge-only."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-axis-b-virtual-resolve-pinned`.

## What happened

## Orthogonal axes (prerequisite)

| Axis | Concern |
|------|---------|
| **Content** | knowledge = judgment; raw = evidence; knowledge carries `sources:` to raw (and local knowledge) |
| **Composition (Axis B)** | Which stores participate and how they resolve at read time |

Do not overload one L1/L2/L3 numbering for both axes.

## Composition layers (Counter 4, hardened)

```text
L1  most-specific write/read root for this context
L2  next layer (e.g. shipped skill package when L1 is project)
L3  mesh peers (explicit edges only)
```

**Context-dependent L1 (A.3):**
- Building knowledge **under skill references** → L1 = that skill’s `references/` wiki  
- Building knowledge **using a skill in a project** → L1 = project overlay (`.agents/…`), L2 = skill package, L3 = related agents/skills  

**Writes (A.3):** only to **L1** (real write-root). Never write into the virtual view, L2, or L3 peers without a separate promotion/gate path.

## Counter A — Virtual filesystem interpretation (PINNED)

Axis B is a **read-only virtual resolve filesystem**: compose knowledge from L1 → L2 → L3 edges into a view the agent can **read**. It is **not** a single mutable disk.

### A.1 — Resolve view, not hard path-merge only (PINNED)

- Default: **federated / ranked visibility** — same logical topic in L1 and L2 can both surface (L1 preferred; L2 retained as base/dispute).  
- Hard path-shadowing is optional, not the sole semantic.  
- Every hit tagged: `store_id` + layer + confidence.

### A.2 — Think-effort hop limits (PINNED)

| Think effort | Max L3 hops |
|--------------|-------------|
| **Low** | 1 |
| **Balanced** | 3 |
| **High** | 5 |
| **Deep** | 10 |

L1+L2 always in scope for the active context; hop budget applies to **mesh (L3)** traversal.

### A.3 — Writes only at L1; layers shift by context (PINNED)

- Virtual resolve is **read-only**.  
- All knowledge/raw writes go to the **current L1** real root.  
- L1 meaning depends on context (skill-train vs project-use) as above.

### A.4 — Cross-store links are knowledge→knowledge only (PINNED)

- **Cross-module / cross-store references** point at **other indexes or knowledge pages**, never at foreign **raw**.  
- Knowledge is the neural connection between modules.  
- If a module’s evidence changes, what **mutates** is the **knowledge** layer (re-judgment); raw remains evidence under its owning store.  
- Local (same-store) knowledge may still `sources:` to its own raw (content-axis provenance).

## Runtime brain

```text
brain_view = resolve(L1, L2, L3_edges)
  under policy: confidence floor, think-effort hops, read-only VFS
write_root = L1 only
```

## Non-goals (this pin)

- Auto-mesh all available brains on install  
- Writable union mount into peer packages  
- Cross-store raw citation as graph edge  

## Related

- Content-axis pins: knowledge↔raw, confidence, wire L1+L2 local provenance  
- L3 detailed design: still TODO under this vocabulary

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
