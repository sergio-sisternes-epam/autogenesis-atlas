---
type: experience
title: "Autogenesis initialise capability implemented"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Added initialise path and updated root SKILL.md so Autogenesis can initialise brand-new packages from scratch by fusing genesis"
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-initialise-capability-implemented`.

## What happened

## What the user asked
User reported that attempting to create a new skill from scratch via autogenesis produced a hard rejection and deferral to genesis. Expected behaviour was that autogenesis would help initialise the skill, and that initialisation must be harness-agnostic. Feedback was captured via skill-feedback (Type: missing-capability, Severity: blocker). Discussion locked the design decisions; formal design was produced and approved; implement path was then executed.

## What we did
- Persisted formal design plan at `artifacts/autogenesis-plans/2026-08-18-initialise-capability.md`.
- Created new path module `references/paths/initialise.md` implementing the full inform → confirm → lock subject → mint v0.1.0 → substrate genesis → fuse layers → mandatory ## Genesis Artifacts → stop-for-approval sequence.
- Updated root `SKILL.md`:
  - description now includes initialise / create-new-skill triggers and the fusion principle
  - version bumped to 2026-08-18.2
  - capabilities table gained the initialise row
  - non-goals rewritten to replace the hard ban on from-scratch authoring with the fusion guardrail and harness-agnostic / no-hand-craft rules
- No knowledge pages were created or materially updated in this Run.

## Pinned decisions (from discussion + design)
- Autogenesis is a fused superset of genesis for new packages.
- On from-scratch request: inform + ask for confirmation.
- Full ## Genesis Artifacts section remains mandatory.
- Subject locked immediately on confirmation; version minted as v0.1.0.
- Folders are merged in the joint plan.
- Genesis capabilities are never superseded or overwritten.

## Changed files
- `references/paths/initialise.md` (new)
- `SKILL.md` (description, version, capabilities table, non-goals, intro paragraph)
- `artifacts/autogenesis-plans/2026-08-18-initialise-capability.md` (new, design plan)

## Ingest deferral
No knowledge pages were created or materially updated; durable conclusions already live in the design plan and the new path module. Explicit deferral of wiki-ingest for this Run.

## Related
- [[raw/experiences/2026-08-16-autogenesis-skill-implemented]]
- Design plan: artifacts/autogenesis-plans/2026-08-18-initialise-capability.md

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
