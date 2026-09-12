---
type: experience
title: Implement advice for Autogenesis SOLID keep/fuse
created: 2026-09-12
work_id: 2026-09-12-solid-architecture-review
status: complete
subject: autogenesis
origin: derived
sensitivity: internal
description: How to implement the keep/fuse plan after explicit G4 approval without contaminating PR 15 or adding runtime machinery.
relates_to:
  - path: autogenesis/work/2026-09-12-solid-architecture-review.md
    kind: implements
  - path: autogenesis/plans/2026-09-12-solid-architecture-review.md
    kind: related
---

# Implement advice for Autogenesis SOLID keep/fuse

## Context

The operator asked to store implementation-plan details after the SOLID
architecture review. This page is advice, not implement authority.

## What happened

Recommended implement sequence after explicit approval of
`autogenesis/plans/2026-09-12-solid-architecture-review.md`:

1. Branch from current GitHub default main. Do not expand
   sergio-sisternes-epam/autogenesis#15. Do not silently retarget its
   gitlink `6746d609f3bcfe91f59d783c29a14b362629b642` unless a later
   governed `store_contract` pin is part of that new change set.
2. Load workspace Autogenesis from the checkout. Catalog v0.4.3 is not
   evidence. Record `skill_root`.
3. Fuse think-grill and think-ramble into workflow-discipline or think-challenge
   only if they remain Run-local and always co-loaded. Update the root
   registry and `invocation-contract.json` in the same change. Do not fuse
   think-challenge; it is the design gate.
4. Thin root SKILL.md so Atlas/approval/substrate prose lives once in
   workflow-discipline. That may close protostar
   `autogenesis/plans/2026-09-12-14-root-prose-dedupe.md`.
5. Keep invocation JSON for repository checkers. Do not teach derived skills
   to emit Autogenesis request envelopes.
6. Extend existing source-contract tests and current-suite smokes only. No new
   Python script file. Preserve smokes `no-new-runtime-module` and
   `workspace-source-not-catalog`.
7. Run Python 3.12 unit tests, release/dependency/store checks, and Atlas
   compile. Persist implement evidence on this work_id. Pin `store_contract`
   only if the parent gitlink must advance.
8. Leave parked protostars unimplemented unless the approved plan names them:
   skill-root-qualified loads, compact evidence examples, scenario-count
   decoupling.

## Outcome

Implementers have an ordered slice, isolation rules for PR #15, and the
SOLID named consequences `fuse-thin-support`, `no-adapter`, `governed-change`,
and `keep-root` for derived simple skills.
