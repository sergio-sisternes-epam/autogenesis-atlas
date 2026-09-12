---
type: experience
title: Shared template path hardening implemented
created: 2026-09-12
work_id: 2026-09-12-9-shared-template-path-hardening
status: recorded
origin: derived
sensitivity: internal
implements: 2026-09-12-9-shared-template-path-hardening
closes:
  - 2026-09-12-9-shared-template-path-hardening
plan_path: autogenesis/work/2026-09-12-9-shared-template-path-hardening-protostar.md
construct_eval: deferred
description: Generalized source coverage now audits concrete resource references across all live Autogenesis module entrypoints.
relates_to:
  - path: autogenesis/work/2026-09-12-9-shared-template-path-hardening.md
    kind: implements
  - path: autogenesis/experiences/2026-09-12-pr7-missed-shared-template-paths.md
    kind: follows
---

# Shared template path hardening implemented

## Context

PR #7 fixed two known package-shared template paths, but its regression test
enumerated only those modules. Issue #9 requested deterministic coverage for
the full live module inventory without adding runtime machinery.

## What happened

The focused assertion was replaced with a structural audit of every
`references/modules/*/SKILL.md`. Concrete resource paths now fail when a
package-shared asset is bare, a declared skill-root or module-local resource
does not exist, or a sibling module is addressed directly instead of through
the parent registry. Mutation cases prove each failure mode. Two external Atlas
path references were rewritten as named path-module loads so they no longer
look module-local.

## Outcome

All 48 repository unit tests, release readiness, dependency and store
contracts, source audit, and both consumer profiles passed. Construct
evaluation was deferred because this is deterministic source-contract
hardening and Autogenesis has no external evaluator dependency.

## Changed files

- `scripts/test_source_contract.py`
- `references/modules/atlas-migrate/SKILL.md`
- `references/modules/workflow-discipline/SKILL.md`

## Related

- GitHub issue: https://github.com/sergio-sisternes-epam/autogenesis/issues/9
- Originating pull request: https://github.com/sergio-sisternes-epam/autogenesis/pull/7

## Follow-ups

GitHub CI remains the final merge gate.
