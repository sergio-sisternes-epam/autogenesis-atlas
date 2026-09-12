---
type: experience
title: "Implemented explicit Discuss package integration"
created: "2026-09-12"
work_id: "2026-09-12-explicit-discuss-integration"
implements: "2026-09-12-explicit-discuss-integration"
closes: "2026-09-12-explicit-discuss-integration"
plan_path: autogenesis/plans/2026-09-12-explicit-discuss-integration.md
construct_eval: "deferred: the installed construct executable cannot import its Python module"
status: done
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-09-12-explicit-discuss-integration.md
    kind: implements
  - path: autogenesis/plans/2026-09-12-explicit-discuss-integration.md
    kind: related
---

## Context

The approved design replaced the embedded Autogenesis `path: discuss` adapter
with the existing explicit and immutable `discuss@atlas` direct dependency.
The user explicitly waived agent-spec `specify` for this implementation.

## What happened

Removed the local discussion path, discussion-mode routing, and adapter-only
scenarios. Updated the root skill, workflow discipline, activation-card
extension, implementation path, record template, release version, package
documentation, scenario references, and deterministic source/release tests.
The new adversarial scenario verifies dependency preservation, adapter absence,
external Discuss routing, and formal-design re-entry.

The prescribed repository unit suite, release-readiness, dependency, source
audit, and direct adversarial smoke all passed. Construct evaluation is
deferred: `/opt/homebrew/bin/construct` fails before execution because it
cannot import `construct.cli`.

## Outcome

Autogenesis v0.6.0 exposes only its own Run paths. Durable discussion is
explicitly delegated to the catalog Discuss package. A discussion conclusion
requiring a package change must start formal Autogenesis design and receive
persisted-plan approval before implementation.

## Changed files

- `.github/ISSUE_TEMPLATE/bug_report.md` (updated)
- `AGENTS.md` (updated)
- `CHANGELOG.md` (updated)
- `CONTRIBUTING.md` (updated)
- `README.md` (updated)
- `SKILL.md` (updated)
- `apm.yml` (updated)
- `references/modules/patterns/activation-card.md` (updated)
- `references/modules/workflow-discipline.md` (updated)
- `references/paths/discuss.md` (deleted)
- `references/paths/implement.md` (updated)
- `references/run-record-template.md` (updated)
- `references/scenarios/atlas-storage-semantics-adversarial-v1.yaml` (updated)
- `references/scenarios/discuss-activation-adversarial-v1.yaml` (deleted)
- `references/scenarios/discuss-activation-adversarial-v2.yaml` (deleted)
- `references/scenarios/explicit-discuss-integration-adversarial-v1.yaml` (created)
- `references/scenarios/specify-only-adversarial-v1.yaml` (updated)
- `scripts/test_release_readiness.py` (updated)
- `scripts/test_source_contract.py` (updated)
