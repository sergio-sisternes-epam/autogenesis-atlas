---
type: experience
title: "PINNED master: composition axis (A\u2013E) + future backlog"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "IMPORTANT consolidated memory of all composition-axis pins, content-axis prerequisites, and TODO tasks for L3/mesh implement."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-composition-axis-all-pins-and-backlog`.

## What happened

## Content axis (prerequisite, agreed)

| Pin | Rule |
|-----|------|
| Knowledge | Judgment / reasoning (primary for answers) |
| Raw | Evidence / memory; may conflict; not authoritative alone |
| Provenance | Knowledge `sources:` → raw (and local knowledge/modules) |
| Confidence | Unwired knowledge = low confidence |
| Local wire | okf-wiki owns L1+L2 local wiring (`wire` CLI); agent-brain calls it |

## Composition axis — named layers only (B3)

| Name | Role |
|------|------|
| **project** | Most-specific root for context (often `.agents/…`; or skill references when training the skill) |
| **package** | Shipped skill/agent `references/` wiki |
| **mesh** | Explicit knowledge→knowledge navigation paths between stores |

No L1/L2/L3 digits for composition.

---

## Counter A — Virtual resolve (pinned)

- Axis B = **read-only virtual resolve**, not writable union disk  
- **A.1** Federated/ranked visibility; hits tagged store + layer + confidence  
- **A.2** Think-effort hops: Low **1** · Balanced **3** · High **5** · Deep **10**  
- **A.3** Writes only to active **project** write-root (context-defined); never into virtual view  
- **A.4** Cross-store links = **knowledge → knowledge** only (never foreign raw)

## Counter B — Naming (pinned B3)

- Use **project · package · mesh** only  

## Counter C — Mesh contamination (pinned)

> Mesh = explicit knowledge→knowledge navigation paths between stores. No default mount of all brains. Read/write on project and package; mesh only by following declared knowledge links under hop/effort limits.

## Counter D — Package promotion (pinned D4)

| Mode | Rule |
|------|------|
| Project use | Write **project** only |
| Skill train | May write **package** + mandatory **human report** (what / rationale / evidence / risks) |
| Cross-project | Recurrence → proposal → **human approval** |
| APM packages | **Issue / PR** on package git repo |
| Grok Cloud | Direct edit possible but **dangerous**; still needs explicit human judgment |

## Counter E — Runtime brain (pinned E1+E2)

- **E1:** Runtime brain = **policy-resolved view**, not bag-of-all-files  
- **E2:** Serious runs emit a **resolve receipt**: stores touched, mesh hops used, confidence floor, write-root  

```text
brain_view = resolve(project, package, mesh_paths)
  under: hop budget, confidence floor, read-only
write_root = project only (or package under skill-train + report)
```

---

## Future tasks (backlog)

### Design (next formal Autogenesis runs)

1. **L3 / mesh detailed design** under this vocabulary  
   - Edge record shape (from knowledge, to knowledge, relation type, confidence)  
   - Registry location (package vs agent-brain host)  
   - Cite vs durable edge  
   - Deny-by-default mount; edge creation on known dependency  
2. **Resolve API / receipt format** (E2 machine shape)  
3. **Think-effort → hop** wiring in agent-brain / okf-wiki query paths  
4. **Promotion report template** for skill-train package updates (D4)  
5. **APM channel** — Issue/PR body template from promotion proposals  

### Implement (after design approval)

6. Mesh edge CRUD (explicit add/list; no auto-full-mesh)  
7. Resolve + receipt on Learn/Train/reevaluate when multi-store  
8. Query progressive disclosure along knowledge paths (index → procedure)  
9. Tests: no bag-mount; hop limits; write-root isolation; no foreign raw cites  

### Out of scope until designed

- Writable union mount  
- Auto-interconnect all skills on install  
- Cross-store knowledge → raw  

## Source experiences

- [[raw/experiences/2026-08-21-axis-b-virtual-resolve-pinned]]
- [[raw/experiences/2026-08-21-composition-layers-named-b3]]
- [[raw/experiences/2026-08-21-mesh-knowledge-paths-pinned]]
- [[raw/experiences/2026-08-21-package-promotion-d4-pinned]]
- (this file for E1+E2 + master backlog)

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
