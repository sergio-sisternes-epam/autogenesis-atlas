---
type: work
title: Skill modules and invocation discipline
created: 2026-09-11
work_id: 2026-09-11-skill-module-invocation
status: deferred
description: Local 0.5.0 source implemented; release review identified an open deployment-validation boundary blocker, with final CI and live acceptance still pending.
relates_to:
  - path: autogenesis/experiences/2026-09-11-module-migration-release-review.md
    kind: related
  - path: autogenesis/work/2026-09-11-skill-module-invocation-execution.md
    kind: related
  - path: autogenesis/experiences/2026-09-11-module-invocation-implementation.md
    kind: related
  - path: autogenesis/plans/2026-09-11-skill-module-invocation.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-skill-module-evolution.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
    kind: related
  - path: autogenesis/experiences/2026-09-11-module-invocation-design.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-module-activation-boundary.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-module-role-scope.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-invocation-execution-scope.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-invocation-request-contract.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-invocation-lifecycle.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-activation-card-presentation.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-module-loader-probe.md
    kind: related
---

# Skill modules and invocation discipline

## Scope

One private Autogenesis root-skill package. Repackage 21 existing instruction
units, define the parent-owned invocation protocol, and coordinate removal
of the old live repository-owned surface. No external/global consumer updates.

## Status

**Implemented locally; final acceptance pending.** The user approved local
checks and GitHub CI as the final gate.
The earlier Phase 0 stop below is historical and no longer blocks source edits.
The canonical design records the amendment and its evidence limits.

Latest release-candidate panel review retained one confirmed deployment-path
ownership blocker after rejecting two false positives. Product source was not
changed by that review. See the review outcome below; prior S8 diagnostic
questions and its unapproved implementation plan remain separate and open.

Historical Phase 0 position: formal design and execution plan remained approved; explicit
start request received on 2026-09-11 at 11:21 +01:00. Release target 0.5.0.
The pinned archive and Copilot root-only discovery have partial evidence.
Python 3.12 baseline is complete. Verified Linux runtime execution and eight
other hosts' actual discovery evidence remain unavailable. The earlier named
token blocker was incorrect: existing gh authentication has private read access,
and the dependency-free local feasibility fixture needs no private credential.
At that checkpoint there were no production changes or migration workers.

Current local integration: all 21 module entrypoints, the root registry,
invocation authority, v0.5.0 docs, consumer checks, and 11 current scenario
suites are present. After checker and independent-review corrections, the
settled Python 3.12 suite passed 68 tests plus source, dependency, release and
store checks. Both tracked
and untracked source assets passed APM audit. Both consumer profiles passed
installation, frozen replay and audit against the settled source. A separate
isolated root manifest/lock replay was byte-identical. Positive and malformed
trace CLI fixtures behaved as expected; these remain structural evidence only.
Independent review completed with two source-reference findings, both corrected
with regression cases. Historical scenarios, root lock and reviewed gitlink are
unchanged. Final GitHub CI and live behavioural evaluation remain outstanding;
this work is not closed or released.

## Outcomes

- [Release-candidate panel review](../experiences/2026-09-11-module-migration-release-review.md) - needs rework: traversal-shaped ownership keys escape package/export boundaries
- [Approved execution plan and model delegation](2026-09-11-skill-module-invocation-execution.md)
- [Implementation experience and current evidence](../experiences/2026-09-11-module-invocation-implementation.md)
- [Formal design](../plans/2026-09-11-skill-module-invocation.md)
- [Design experience and evidence](../experiences/2026-09-11-module-invocation-design.md)
- [Original discussion](../discussions/2026-09-11-skill-module-evolution.md)
- [Illustrations and vocabulary evolution](../discussions/2026-09-11-module-model-walkthrough.md)
- [Parent routing decision](../discussions/2026-09-11-module-activation-boundary.md)
- [Uniform packaging decision](../discussions/2026-09-11-module-role-scope.md)
- [Instruction-protocol scope](../discussions/2026-09-11-invocation-execution-scope.md)
- [Protected context ownership](../discussions/2026-09-11-invocation-request-contract.md)
- [Retry eligibility and two-attempt bound](../discussions/2026-09-11-invocation-lifecycle.md)
- [Full/compact card decision](../discussions/2026-09-11-activation-card-presentation.md)
- [Cutover scope and pending deployment proof](../discussions/2026-09-11-module-loader-probe.md)

The execution companion defines 33 dependent tasks, including one per module.
Six agent roles use risk-based model selection and at most three simultaneous
delegated workers. Source work follows the approved local/CI gate amendment.
Construct remains unavailable locally because its executable cannot import the
`construct` module. Scenario command smoke checks are not live agent evaluation.
