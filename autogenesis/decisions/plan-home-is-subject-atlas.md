---
type: decision
title: "Design plans live in Autogenesis space plans/ (type plan)"
created: 2026-08-23
status: accepted
work_id: autogenesis-plan-home-subject-atlas-v1
description: "Subject Atlas SCHEMA includes type plan and autogenesis_space.plans_dir. Plans are plans/<work_id>.md — not experiences. Missing Atlas still triggers initiate/migrate offers."
relates_to:
  - path: autogenesis/work/autogenesis-plan-home-subject-atlas-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: follows
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
---

## Decision

1. **Plan home** = subject Atlas **Autogenesis space**: `plans/<work_id>.md` with frontmatter `type: plan`.
2. SCHEMA must declare `templates.by_type.plan`, recommended type `plan`, and `autogenesis_space` (`plans_dir`, `plan_path_convention`, `initiate_includes`).
3. Plans are **not** stored as `type: experience`.
4. **`plan_path`** is Atlas-relative (`plans/<work_id>.md`).
5. **If no Atlas:** inform user; offer initiate Atlas (bootstrap includes `plans/` + plan template) and, when okf-wiki exists, migrate; or abort.
6. `artifacts/autogenesis-plans/` is not the primary plan home.

## Rationale

Experiences record what happened; plans are a distinct artifact with genesis sections and approval status. A dedicated folder and type make the Autogenesis space queryable and prevent mixing run narrative with design packets.

## Alternatives considered

- Keep plans as experiences with a naming convention — rejected (wrong type, weak SCHEMA, pollutes experience indexes).
- Global artifacts/ only — rejected (splits graph from subject memory).

## Consequences

- Initiate-Atlas bootstrap for Autogenesis subjects must create `plans/`, `plans/index.md`, and `templates/plan.md`.
- design / initialise / reevaluate write `type: plan` pages under `plans/`.
- Compile remains the green gate after plan persist.
