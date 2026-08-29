---
type: experience
title: "2026-08-16 Skill-feedback: autogenesis failed to enforce subject memory/lineage on apm run"
created: 2026-08-16
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Blocker: product artifacts existed but subject okf-wiki graph and lineage exit ticket were incomplete. User requires hard gate for memory generation."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-16-skill-feedback-memory-gate-failure-apm-run`.

## What happened

## Observation
After a long Run on subject `apm` (corpus, grill, layer plan, Layer 0–2 implement), user asked whether memory of the work existed. Audit showed:
- Present: `apm/SKILL.md`, `apm/references/*.md`, `artifacts/autogenesis-plans/*`
- Missing from subject wiki: design notes, grill Q&A trail, procedure module pages, raw microsoft/apm captures with git provenance, lineage/reflection exit ticket

## User rule (normative)
Autogenesis should **always gate and enforce** memory generation for provenance and future work — same class of discipline as approval-before-implement.

## Diagnosis (claimed vs applied)
- Lineage-as-exit-ticket and subject-wiki ownership were **loaded** from SKILL.md but only **partially applied**.
- “Proceed/Continue” advanced implementation layers without a blocking memory-integrity close.
- Mid-session filesystem loss of `.grok/skills/apm/references/wiki/**` amplified the gap; process did not stop with `incomplete: missing memory gate` or mandatory restore+validate.

## Failure class
Partial rule application of Run adherence (memory/lineage gates); environmental non-durability of deep wiki trees vs product/artifacts paths.

## Required process change
Treat subject-wiki validate + lineage/reflection experience + (ingest or explicit deferral) as **blocking** exit criteria before any Run may be presented as complete.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
