---
type: experience
title: Decoupling Autogenesis from the unavailable private evaluator
created: 2026-09-11
work_id: 2026-09-11-remove-construct-binding
implements: 2026-09-11-remove-construct-binding
closes:
  - 2026-09-11-remove-construct-binding
plan_path: autogenesis/plans/2026-09-11-remove-construct-binding.md
status: done
origin: internal
sensitivity: internal
description: Removed the private evaluator from live Autogenesis contracts, replaced its gate with portable scenarios and repository-native evidence, and retained historical provenance.
relates_to:
  - path: autogenesis/work/2026-09-11-remove-construct-binding.md
    kind: implements
  - path: autogenesis/plans/2026-09-11-remove-construct-binding.md
    kind: records
  - path: autogenesis/experiences/2026-09-11-instruction-first-module-implementation.md
    kind: follows
---

# Decoupling Autogenesis from the unavailable private evaluator

## Context

The user decided that Autogenesis must not require Construct because that
private evaluator will not be open sourced in the foreseeable future. The
approved plan removed the binding without replacing it with another framework,
weakening evidence requirements, or rewriting historical records.

This forward-only change applies to the live root skill, parent-routed modules,
shared templates, current scenario selection, documentation, and future
lineage fields. Historical scenario bodies and earlier Atlas experiences retain
their original evidence and terminology.

## What happened

- Root routing and workflow guidance now describe evaluator-neutral portable
  scenarios, direct repository checks, actual evidence, precise deferrals, and
  GitHub CI as the final release gate.
- Design emits a full portable scenario draft. Implement runs every applicable
  command with available tools and cannot infer success from prose.
- Future work records use `scenario_ref` and `evaluation_evidence`; the
  evaluator-specific lineage fields were removed from the live template and
  implementation contract.
- `autogenesis-adversarial-v4.yaml` became current, v3 moved to the immutable
  historical set, and the successor map records v3 to v4.
- Source-contract inventory now covers 14 current and 13 historical scenarios.
- No replacement evaluator, runner, service, dependency, or generated protocol
  was introduced.

The v4 diagnostic necessarily names the prohibited dependency in its work
lineage and search expression. That is test provenance, not a live runtime
binding. Its smoke scans the actual root, module entrypoints, and shared
templates, where no product binding remains.

## Outcome

All six command-backed v4 smokes passed. The Python 3.12 repository suite
passed 73 tests. The source contract reported 21 modules, 21 entrypoints,
21 registry rows, and 27 scenario files with no errors or warnings.

Release metadata, dependency, and store contracts passed. The isolated source
audit checked 51 files with zero failures. Both APM 0.30.0 consumer profiles
passed initial install, frozen replay, owned-content validation, and audit:
Agent Skills plus the nine stable runtime targets.

Live `SKILL.md`, `references/modules/*/SKILL.md`, and
`references/templates/*.md` contain no Construct product binding. GitHub CI
remains the final release gate; it was not run locally. The independently
reviewed ownership-ledger traversal defect remains separate and unchanged.

The instruction-first guidance is therefore locally complete rather than
blocked on the unavailable evaluator. S8 remains draft pending repeated
observed use and a separate admission decision; optional independent
comparative evaluation may add evidence later but is not a runtime dependency
or local implementation gate.

No commit, push, tag, release, repository-setting change, or global consumer
update occurred.

