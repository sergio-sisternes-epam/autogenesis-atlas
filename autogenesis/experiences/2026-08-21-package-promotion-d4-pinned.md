---
type: experience
title: "PINNED: Package promotion D4 (project vs package, APM vs Grok)"
created: 2026-08-21
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "IMPORTANT. Project-use writes project only. Skill-train may improve package with human-facing report. Cross-project promotion via recurrence + approval. APM = Issue/PR to git; Grok Cloud direct edit allowed but dangerous and still needs explicit human judgment."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-21-package-promotion-d4-pinned`.

## What happened

## Core hybrid (D4)

| Mode | Write root | Package change |
|------|------------|----------------|
| **Using a skill in a project** | **project** only | No silent package writes |
| **Training the skill** (`target: skill`) | **package** (that skill’s `references/`) | Allowed under Train/Learn discipline, but **not silent**: agent must present a **change report** to humans |
| **Cross-project elevation** (D2) | — | **Recurrence signal** → promotion **proposal** only → **human approval** required |

## Training-time package self-improve (D3 refined)

When training a skill and the agent updates **package** knowledge/contracts:

1. Apply changes only under explicit skill-train context.  
2. **Present a report back to humans** including:
   - **what** changed (paths, knowledge pages, contracts)
   - **rationale** (why the skill surface should evolve)
   - **evidence** (raw/knowledge pointers, train stages, failures fixed)
   - **risks / residual uncertainty**
3. Human judges: keep, revert, or open formal design/PR path.

Self-improve ≠ silent ship. Report is mandatory product behaviour.

## Cross-project promotion (D2 refined)

- Same proposal/gap **signature** across multiple projects or sessions → emit **promotion proposal** (not auto-merge into package).  
- **Human approval** required before package absorbs the pattern.  
- Aligns with autogenesis reevaluate → challenged plan → user judgment when evolution-worthy.

## Channel by packaging regime

| Regime | How package changes land |
|--------|---------------------------|
| **APM-managed package** (git-backed skill repo) | **Issue and/or Pull Request** to the package’s git repo. No silent push to mainline without human review. |
| **Grok Cloud / in-harness skills** (editable tree here) | Direct skill update is *technically* possible and **dangerous**. Still requires **explicit human judgment** (report + approve). Prefer treating direct edit as “draft applied locally” until human confirms; do not equate “file written” with “generalised package truth.” |

## Hard rules

- Mesh paths never grant write into a peer **package**.  
- Project experience does not become package law without recurrence + approval (APM: PR/Issue; Grok: human confirm after report).  
- Under-promote (never improve package) and over-promote (absorb one-off hacks) are both failures; D4 is the middle path.

## Related

- [[raw/experiences/2026-08-21-axis-b-virtual-resolve-pinned]]
- [[raw/experiences/2026-08-21-mesh-knowledge-paths-pinned]]
- Post-Learn challenged plan handoff (user judgment before implement)

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
