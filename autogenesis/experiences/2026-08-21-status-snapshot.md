---
type: experience
title: "Status snapshot 2026-08-21 \u2014 agent-brain / okf-wiki / mesh"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Point-in-time memory of shipped capabilities, versions, composition pins, and remaining backlog. Use to orient fresh sessions."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-status-snapshot`.

## What happened

## Versions (semver only)

| Skill | Version |
|-------|---------|
| okf-wiki | **0.3.0** |
| agent-brain | **0.3.0** |
| autogenesis | **0.2.0** |
| okf | 0.1.0 |
| knowledge-crawl | 0.1.0 |
| terraform | 0.1.0 |

Rule: all skills use **MAJOR.MINOR.PATCH** only (no date stamps).

## Content axis (shipped)

- **knowledge** = judgment; **raw** = evidence  
- Knowledge `sources:` → local raw and/or local knowledge/modules  
- **wire** CLI merges sources + `confidence` high|low  
- Unwired knowledge = low confidence; blocking task on incomplete wiring  

## Composition axis (pinned + mesh v1)

| Layer | Role |
|-------|------|
| **project** | Most-specific write/read root for context |
| **package** | Shipped skill/agent `references/` wiki |
| **mesh** | Explicit knowledge→knowledge paths only |

- Read-only **virtual resolve** (not writable union disk)  
- Hops by think effort: low 1 · balanced 3 · high 5 · deep 10  
- Writes: project (or package under skill-train + human report)  
- Promotion D4: recurrence + approval; APM = Issue/PR; Grok direct edit dangerous  
- Runtime brain = policy-resolved view + **resolve receipt** (E2) on multi-store/hops  

### Mesh CLI (okf-wiki 0.3.0)

`mesh list` · `mesh add` · `mesh resolve` → `mesh/edges.jsonl`  
Relation allowlist; soft cap 50; dead edges skipped; never full-scan all stores.

Smoke: terraform → okf-wiki edge resolved with hop=1 + path receipt.

## agent-brain cognitive loop (shipped)

- **Learn** + **Train** (unattended stages; plan/todo; claim=action ingest)  
- Post-material Learn → **autogenesis reevaluate** → proposals / challenged plan / target todo / **user decision packet**  
- Overlay routing (skill wiki vs project `.agents/`)  
- Unresolved tasks: document and continue; user recalls list  

## Explicitly not shipped

### Modules
dream · think · forget · decide/plan  

### Open ADRs
- **ADR-001** infinite conflict loops  
- **ADR-002** cross-skill/cross-repo joint fixes (default: pure handover)  

### Mesh / composition remaining
1. Reverse dependency index  
2. Full **project**-layer resolve roots  
3. Think-effort wired through agent-brain paths (not only CLI)  
4. Progressive disclosure UX (index → procedure)  
5. Isolation/hop/write tests  
6. Skill-train **package change report** path module  
7. APM Issue/PR body templates  
8. Dead-edge notify on target rename  

### Thin mechanisms
Unresolved-task list schema · conflict signatures · richer handover schema · scheduled task surface  

### Out of scope until design
Writable union mount · auto-mesh-all · cross-store knowledge→raw  

## Key experiences

- `composition-axis-all-pins-and-backlog`  
- `implement-mesh-composition`  
- `pending-backlog-v0.1`  
- `semver-consistency-decision`  
- mesh design plan: `artifacts/autogenesis-plans/mesh-composition-axis-design-2026-08-21.md`  

## Three-axis composition (pinned later same day)

Content · Store composition (project/package/mesh) · Capability (manifest requires).  
Capability deps may carry knowledge entry deps (scenario); domain↔domain mesh prefers project.

## Orient next session

1. Load this snapshot + composition master pin  
2. Do not bag-mount peer wikis; use mesh edges  
3. Prefer skill-train package writes only with human report  
4. New work on dream/ADRs/mesh follow-ups needs explicit design Run

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
