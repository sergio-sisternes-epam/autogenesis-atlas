---
type: experience
title: One-question-at-a-time module invocation design
created: 2026-09-11
work_id: 2026-09-11-skill-module-invocation
status: recorded
plan_path: autogenesis/plans/2026-09-11-skill-module-invocation.md
subject: autogenesis
relates_to:
  - path: autogenesis/work/2026-09-11-skill-module-invocation.md
    kind: implements
  - path: autogenesis/plans/2026-09-11-skill-module-invocation.md
    kind: records
  - path: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
    kind: derived_from
---

# Module invocation design

## Context

The user proposed replacing flat path documents with skill-shaped nested
modules. Through discussion they approved parent routing, uniform operation/
support packaging, and the activation card as a visible cue for a request.
They then requested one question at a time and memories of every discussion
and decision, followed by a complete design.

## What happened

Sequential choices established an instruction-based protocol, parent-owned
protected context, compact supporting cards, and full root/operation cards.
The user rejected the suggested no-automatic-retry policy: they selected one
retry for transient failures with known-safe repetition. They also rejected
the proposed long-lived compatibility adapters: all live repository-owned
consumers migrate together, with the old surface removed in the first release.
External repositories and installed/global consumers remain out of scope.

Every selection was persisted in its discussion node and compiled before the
next question. A formal design Enter then classified the work as new-surface.
Genesis, the internal challenge module, the patterns extension, Atlas, and OKF
were loaded. No internal challenge was invoked as a discussion user verb.

Two public searches investigated nested discovery and retry failure modes.
The primary Agent Skills specification and AWS reliability guidance grounded
the counters. A bounded read-only APM specialist inspected assigned consumer,
dependency, release and installed-package code. The existing 32-test offline
suite passed. Installed APM reported 0.30.0. Native-copy source supports nested
asset retention, but is not proof of CI-artifact identity or actual harness
discovery.

## Evidence findings

- scripts/dependency_contract.py:182-199 contains two loose module paths.
- scripts/validate_consumer.py:126-150 checks immediate root metadata, not
  unwanted differently named owned exports or nested assets.
- scripts/validate_consumer.py:208-222 verifies the selected root hash, not
  every module resource; 255-289 does not repeat all deployment checks after
  frozen replay.
- scripts/test_validate_consumer.py:67-71 intentionally permits dependency
  skills, so a global "only one installed skill" assertion would be wrong.
- Installed apm_cli/integration/skill_integrator.py:1213-1252 and 1533-1559
  copies a native root package and separately promotes .apm/skills children.
  Its deployment may rewrite Markdown links; source-byte equality for all
  files is not a valid unqualified requirement.
- Existing atlas-migrate scenarios contain hardcoded old paths, frontmatter,
  and old release versions. Historical suites must be classified rather than
  relabelled as current successful checks.

## Outcome

Persisted the new-surface formal plan and canonical work hub. The plan includes
three diagrams, all 21 module interfaces, request/card/receipt contracts,
single-owner retry rules, scoped removals, current/historical scenario mapping,
six grounded counters, full happy/adversarial scenario drafts, and an
implementation dependency order. Proposed version: 0.5.0.

agent-spec is unavailable in the active catalogue. Its behavioural Gherkin
and b- IDs are explicitly deferred; no such files were authored or claimed.
New scenario executions, deployment fixtures, actual harness discovery,
with/without-skill content evaluations, and trigger scores remain future
implementation/release gates. No evaluation result was invented.

## Approval and scope

Formal plan approval is pending. No product source, dependency pins, tags,
releases, settings, or global consumers were changed. Existing historical
Discuss lint failures were left untouched. Memory compile is independent
of those historical discussion lint issues.
