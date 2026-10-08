---
type: experience
title: Implementing authored Waza suites and the Autogenesis dogfood suite (0.9.0)
created: "2026-10-08"
updated: "2026-10-08"
work_id: 2026-10-08-waza-evaluation
implements: 2026-10-08-waza-evaluation
closes:
  - 2026-10-08-waza-evaluation
plan_path: autogenesis/plans/2026-10-08-waza-evaluation.md
external_ref: https://github.com/sergio-sisternes-epam/autogenesis/pull/25
status: done
origin: internal
sensitivity: internal
description: Phase 1 and Phase 2 of the Waza evaluation plan (revision 3) are implemented on PR 25 at 7d3ffc8. The agent-spec gate is retired, Autogenesis authors upstream Waza suites under a closed model-free check allowlist, and its own dogfood suite passed the model-free validity checks (reference 7/7 passed, negative 7/7 failed); not run against an agent.
relates_to:
  - path: autogenesis/work/2026-10-08-waza-evaluation.md
    kind: implements
  - path: autogenesis/plans/2026-10-08-waza-evaluation.md
    kind: records
  - path: autogenesis/experiences/2026-09-11-evaluator-decoupling-implementation.md
    kind: follows
---

# Implementing authored Waza suites and the Autogenesis dogfood suite (0.9.0)

## Context

Sergio approved Phase 1 and Phase 2 at 01:25 BST on 2026-10-08: "Go on Phase 1
and Phase 2: implement eval authoring in Autogenesis (v0.9.0), then write its
own suite and hand it to Master of Trials." The approved artefact is the
revision 3 plan. Implementation ran on branch `2026-10-08-waza-evaluation` of
the Autogenesis repository; every product file change was made through fresh
Copilot CLI sessions (model claude-opus-5.5). PR 25 is open and not merged.
The version surfaces say 0.9.0; no tag or release was made (releases belong
to Master of Packages).

## What happened

- **Phase 1 (commit bf2ed92):** retired the agent-spec/Gherkin gate (G-BDD
  became G-BEHAVIOUR; `behavioural_contract: waza | deferred:<reason>`, with
  `specify` rejected by diagnostic). Added the shared guide
  `references/waza-authoring.md`: format pin Waza 0.38.9 (774df00) and schema
  1.4, layout, tiers, authoring rules, grader-trust fixtures, pass-bar
  metadata, the closed V1-V3 allowlist, the `waza_suite` / `validity` evidence
  block, the run boundary with the separate on-demand evaluator bot as
  intended runner, and the `supplied_results` citation block. Updated
  workflow-discipline, design, implement, initialise, the invocation contract
  and the work-node template. Added `waza-evaluation-adversarial-v1.yaml`
  (22 smokes) and the parse-valid successor
  `help-getting-started-adversarial-v2.yaml`; moved
  `specify-only-adversarial-v2` and `help-getting-started-adversarial-v1` to
  historical with bodies unchanged (index 37: 17 current, 20 historical).
- **Phase 2 (commits b25c95d, 7d3ffc8):** authored `evals/autogenesis/`
  (suite_version 1): five gate tasks, two trigger tasks and one advisory
  quality task with fixture subject repos and reference/negative fixtures for
  the seven deterministic tasks, then ran only the model-free checks and
  recorded them in the suite README.
- Defaults taken for questions the approval did not answer: no `USE FOR:`
  labels (question 3); `evals/` ships in the package tree like
  `references/scenarios/` (question 5, CI consumer installs pass); genesis is
  listed as a required skill in the suite README only (question 6); fixtures
  use a small local store with the placeholder id `example.invalid`
  (question 7); the unparseable current suite was folded into Phase 1 as a
  successor (question 8).

## Evaluation evidence

```text
deterministic:
  unit tests: python3 -m unittest discover -s scripts -p 'test_*.py' -> 58 tests OK locally (PyYAML 6.0.3); CI OK (skipped=2: PyYAML absent there)
  release readiness: version_consistency=pass, release_metadata_decision=pass, commit_consistency=pass (expected_tag=v0.9.0)
  new suites: waza-evaluation-adversarial-v1 22/22, help-getting-started-adversarial-v2 6/6 smokes ok
  all current smokes: 99/119 ok; the 20 failing were already failing at f901d0d (quoting in their cmds); no new failures
  CI on PR 25 @ 7d3ffc8: all 7 checks pass (source integrity, Atlas store, both consumer installs, frozen deps, release metadata, readiness)
waza_suite:
  path: evals/autogenesis/ @ 7d3ffc8985a159cf959bf09b88f49354565b5681
  suite_version: 1
  format: waza 0.38.9, schemaVersion 1.4
  tasks: 8 (gate 5, quality 1, trigger 2)
  coverage: description has no USE FOR / DO NOT USE FOR labels (authored against description text)
  grader_controls: reference + negative fixture for 5/5 gate tasks (and both trigger tasks)
  validity:
    waza: 0.38.9 (image localhost/waza-eval:0.3, rootless Podman, --pull=never --cgroups=disabled --network=none, read-only export of the commit)
    env: WAZA_NO_UPDATE_CHECK=1
    check:
      cmd: waza check . --format json
      exit_code: 0
      summary: eval found (evals/autogenesis/eval.yaml); eval schema valid; skill findings - SKILL.md 3762 tokens vs 500 budget (compliance Medium, ready false), unknown frontmatter fields activation_card and version, no license, no metadata.version, 20 external links dead because the network was off
    spec_verify:
      cmd: waza spec verify --skill . --eval evals/autogenesis/eval.yaml --format json
      exit_code: 0
      coverage: 1 requirement (whole description), 0 covered deterministically
    grader_fixtures:
      cmd: waza grade evals/autogenesis/eval.yaml --task <id> --results evals/autogenesis/fixtures/<id>/<variant>.results.json --workspace evals/autogenesis/fixtures/<id>/<variant>
      checked: 7 deterministic tasks; reference passed 7/7, negative failed 7/7; every grade call exit 0
      left_to_runner: plan-has-genesis-artifacts
    output_log: box-local captures under /workspace/waza-impl/validity/<commit>/ (not durable)
  run_status: not-run-by-autogenesis
```

This is validity evidence, not behavioural evidence. No model call was made
and no suite task was run against an agent.

## Findings

- `waza check` also probes external links over the network. The plan said V1
  makes no network calls beyond the update check; that was wrong. Checks ran
  with networking disabled, and the guide now says to do so.
- `spec verify` cannot cover a long description deterministically: 0 of 1
  without `USE FOR:` labels, which keeps question 3 live.
- CI has no PyYAML, so the scenario-parse and dogfood-structure tests skip
  there; they ran locally. A pinned PyYAML in CI would be a dependency change
  outside this plan.
- Sourcing the box Podman environment from a repository directory leaves an
  empty `oom` file there; it was removed before every commit.

## Changed files

- `.waza.yaml` (added 2026-10-08 02:16 BST approval: SKILL.md token budget 4000)
- `.github/ISSUE_TEMPLATE/bug_report.md`
- `AGENTS.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `SKILL.md`
- `apm.yml`
- `evals/autogenesis/README.md`
- `evals/autogenesis/eval.yaml`
- `evals/autogenesis/fixtures/design-stops-for-approval/negative.results.json`
- `evals/autogenesis/fixtures/design-stops-for-approval/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `evals/autogenesis/fixtures/design-stops-for-approval/negative/SKILL.md`
- `evals/autogenesis/fixtures/design-stops-for-approval/negative/atlas-mesh.json`
- `evals/autogenesis/fixtures/design-stops-for-approval/reference.results.json`
- `evals/autogenesis/fixtures/design-stops-for-approval/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `evals/autogenesis/fixtures/design-stops-for-approval/reference/SKILL.md`
- `evals/autogenesis/fixtures/design-stops-for-approval/reference/atlas-mesh.json`
- `evals/autogenesis/fixtures/discussion-has-no-implement-authority/negative.results.json`
- `evals/autogenesis/fixtures/discussion-has-no-implement-authority/negative/SKILL.md`
- `evals/autogenesis/fixtures/discussion-has-no-implement-authority/negative/atlas-mesh.json`
- `evals/autogenesis/fixtures/discussion-has-no-implement-authority/reference.results.json`
- `evals/autogenesis/fixtures/discussion-has-no-implement-authority/reference/SKILL.md`
- `evals/autogenesis/fixtures/discussion-has-no-implement-authority/reference/atlas-mesh.json`
- `evals/autogenesis/fixtures/help-does-not-mount/negative.results.json`
- `evals/autogenesis/fixtures/help-does-not-mount/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md`
- `evals/autogenesis/fixtures/help-does-not-mount/negative/.gitmodules`
- `evals/autogenesis/fixtures/help-does-not-mount/negative/SKILL.md`
- `evals/autogenesis/fixtures/help-does-not-mount/negative/atlas-mesh.json`
- `evals/autogenesis/fixtures/help-does-not-mount/reference.results.json`
- `evals/autogenesis/fixtures/help-does-not-mount/reference/SKILL.md`
- `evals/autogenesis/fixtures/help-does-not-mount/reference/atlas-mesh.json`
- `evals/autogenesis/fixtures/implement-blocks-without-approval/negative.results.json`
- `evals/autogenesis/fixtures/implement-blocks-without-approval/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `evals/autogenesis/fixtures/implement-blocks-without-approval/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/2026-10-08-add-retry-note.md`
- `evals/autogenesis/fixtures/implement-blocks-without-approval/negative/SKILL.md`
- `evals/autogenesis/fixtures/implement-blocks-without-approval/negative/atlas-mesh.json`
- `evals/autogenesis/fixtures/implement-blocks-without-approval/reference.results.json`
- `evals/autogenesis/fixtures/implement-blocks-without-approval/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `evals/autogenesis/fixtures/implement-blocks-without-approval/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/2026-10-08-add-retry-note.md`
- `evals/autogenesis/fixtures/implement-blocks-without-approval/reference/SKILL.md`
- `evals/autogenesis/fixtures/implement-blocks-without-approval/reference/atlas-mesh.json`
- `evals/autogenesis/fixtures/ordinary-refactor-near-miss/negative.results.json`
- `evals/autogenesis/fixtures/ordinary-refactor-near-miss/negative/app/durations.py`
- `evals/autogenesis/fixtures/ordinary-refactor-near-miss/reference.results.json`
- `evals/autogenesis/fixtures/ordinary-refactor-near-miss/reference/app/durations.py`
- `evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative.results.json`
- `evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-retry-backoff-guidance.md`
- `evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative/SKILL.md`
- `evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative/atlas-mesh.json`
- `evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference.results.json`
- `evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-retry-backoff-guidance.md`
- `evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference/SKILL.md`
- `evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference/atlas-mesh.json`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative.results.json`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative/SKILL.md`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative/atlas-mesh.json`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative/references/atlas/README.md`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative/references/atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative/references/atlas/index.md`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference.results.json`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference/SKILL.md`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference/atlas-mesh.json`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference/references/atlas/README.md`
- `evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference/references/atlas/index.md`
- `evals/autogenesis/fixtures/skill-change-should-trigger/negative.results.json`
- `evals/autogenesis/fixtures/skill-change-should-trigger/negative/SKILL.md`
- `evals/autogenesis/fixtures/skill-change-should-trigger/negative/atlas-mesh.json`
- `evals/autogenesis/fixtures/skill-change-should-trigger/reference.results.json`
- `evals/autogenesis/fixtures/skill-change-should-trigger/reference/SKILL.md`
- `evals/autogenesis/fixtures/skill-change-should-trigger/reference/atlas-mesh.json`
- `evals/autogenesis/fixtures/subjects/python-app/app/durations.py`
- `evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/SCHEMA.json`
- `evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/decisions/index.md`
- `evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/experiences/index.md`
- `evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/index.md`
- `evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/index.md`
- `evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/2026-10-08-add-retry-note.md`
- `evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/index.md`
- `evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md`
- `evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/log.md`
- `evals/autogenesis/fixtures/subjects/subject-designed/SKILL.md`
- `evals/autogenesis/fixtures/subjects/subject-designed/atlas-mesh.json`
- `evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/SCHEMA.json`
- `evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/decisions/index.md`
- `evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/experiences/index.md`
- `evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/index.md`
- `evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/index.md`
- `evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/index.md`
- `evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md`
- `evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/log.md`
- `evals/autogenesis/fixtures/subjects/subject-legacy/SKILL.md`
- `evals/autogenesis/fixtures/subjects/subject-legacy/atlas-mesh.json`
- `evals/autogenesis/fixtures/subjects/subject-legacy/references/atlas/README.md`
- `evals/autogenesis/fixtures/subjects/subject-legacy/references/atlas/index.md`
- `evals/autogenesis/fixtures/subjects/subject-unmounted/SKILL.md`
- `evals/autogenesis/fixtures/subjects/subject-unmounted/atlas-mesh.json`
- `evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/SCHEMA.json`
- `evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/decisions/index.md`
- `evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/experiences/index.md`
- `evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/index.md`
- `evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/index.md`
- `evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/index.md`
- `evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md`
- `evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/log.md`
- `evals/autogenesis/fixtures/subjects/subject/SKILL.md`
- `evals/autogenesis/fixtures/subjects/subject/atlas-mesh.json`
- `evals/autogenesis/tasks/design-stops-for-approval.yaml`
- `evals/autogenesis/tasks/discussion-has-no-implement-authority.yaml`
- `evals/autogenesis/tasks/help-does-not-mount.yaml`
- `evals/autogenesis/tasks/implement-blocks-without-approval.yaml`
- `evals/autogenesis/tasks/ordinary-refactor-near-miss.yaml`
- `evals/autogenesis/tasks/plan-has-genesis-artifacts.yaml`
- `evals/autogenesis/tasks/plan-only-in-resolved-atlas.yaml`
- `evals/autogenesis/tasks/skill-change-should-trigger.yaml`
- `references/modules/design/SKILL.md`
- `references/modules/getting-started/references/first-journey.md`
- `references/modules/help/references/capability-catalog.md`
- `references/modules/help/references/enrichment.md`
- `references/modules/help/references/topics.md`
- `references/modules/implement/SKILL.md`
- `references/modules/initialise/SKILL.md`
- `references/modules/workflow-discipline/SKILL.md`
- `references/modules/workflow-discipline/references/invocation-contract.md`
- `references/scenarios/atlas-migrate-activation-adherence-v4.yaml`
- `references/scenarios/atlas-storage-semantics-adversarial-v3.yaml`
- `references/scenarios/help-getting-started-adversarial-v2.yaml`
- `references/scenarios/suite-index.json`
- `references/scenarios/waza-evaluation-adversarial-v1.yaml`
- `references/templates/work-node.md`
- `references/waza-authoring.md`
- `scripts/test_release_readiness.py`
- `scripts/test_source_contract.py`

## Token budget follow-up

Sergio approved at 02:16 BST raising the Waza token budget for the root
SKILL.md. A root `.waza.yaml` (commit 71b7a1c) sets `SKILL.md` to 4000 and
restates Waza's other built-in limits, because `tokens.limits` replaces them.
Re-run offline at head f43df15 (Waza 0.38.9, network off,
`WAZA_NO_UPDATE_CHECK=1`): `waza check` exit 0, 3762 of 4000 tokens, not
exceeded (status warning, above the unchanged 500-token warning threshold);
compliance still Medium and `ready: false` (no trigger/anti-trigger labels,
unknown frontmatter fields, dead links with the network off). V2 and V3
unchanged: reference 7/7 passed, negative 7/7 failed. CI green on f43df15.

## Outcome

Done on the branch: PR 25 open at 7d3ffc8, CI green, not merged, no release.
Behavioural status: authored-not-run. Hand-off for running goes to Master of
Trials.
