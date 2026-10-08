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
description: Phase 1 and Phase 2 of the Waza evaluation plan (revision 3) are implemented on PR 25 (head 8f076d7). The agent-spec gate is retired and Autogenesis authors upstream Waza suites under a closed model-free check allowlist. After an invalid supplied run (contaminated, no python3), the dogfood suite moved to .apm/evals/autogenesis/ (suite_version 2) and is not shipped; model-free validity re-run green; not yet validly run against an agent.
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

Against the merge base with `main`, at head 8f076d7.

- `.apm/evals/autogenesis/README.md`
- `.apm/evals/autogenesis/eval.yaml`
- `.apm/evals/autogenesis/fixtures/design-stops-for-approval/negative.results.json`
- `.apm/evals/autogenesis/fixtures/design-stops-for-approval/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `.apm/evals/autogenesis/fixtures/design-stops-for-approval/negative/SKILL.md`
- `.apm/evals/autogenesis/fixtures/design-stops-for-approval/negative/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/design-stops-for-approval/reference.results.json`
- `.apm/evals/autogenesis/fixtures/design-stops-for-approval/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `.apm/evals/autogenesis/fixtures/design-stops-for-approval/reference/SKILL.md`
- `.apm/evals/autogenesis/fixtures/design-stops-for-approval/reference/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/discussion-has-no-implement-authority/negative.results.json`
- `.apm/evals/autogenesis/fixtures/discussion-has-no-implement-authority/negative/SKILL.md`
- `.apm/evals/autogenesis/fixtures/discussion-has-no-implement-authority/negative/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/discussion-has-no-implement-authority/reference.results.json`
- `.apm/evals/autogenesis/fixtures/discussion-has-no-implement-authority/reference/SKILL.md`
- `.apm/evals/autogenesis/fixtures/discussion-has-no-implement-authority/reference/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/help-does-not-mount/negative.results.json`
- `.apm/evals/autogenesis/fixtures/help-does-not-mount/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md`
- `.apm/evals/autogenesis/fixtures/help-does-not-mount/negative/.gitmodules`
- `.apm/evals/autogenesis/fixtures/help-does-not-mount/negative/SKILL.md`
- `.apm/evals/autogenesis/fixtures/help-does-not-mount/negative/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/help-does-not-mount/reference.results.json`
- `.apm/evals/autogenesis/fixtures/help-does-not-mount/reference/SKILL.md`
- `.apm/evals/autogenesis/fixtures/help-does-not-mount/reference/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/implement-blocks-without-approval/negative.results.json`
- `.apm/evals/autogenesis/fixtures/implement-blocks-without-approval/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `.apm/evals/autogenesis/fixtures/implement-blocks-without-approval/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/2026-10-08-add-retry-note.md`
- `.apm/evals/autogenesis/fixtures/implement-blocks-without-approval/negative/SKILL.md`
- `.apm/evals/autogenesis/fixtures/implement-blocks-without-approval/negative/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/implement-blocks-without-approval/reference.results.json`
- `.apm/evals/autogenesis/fixtures/implement-blocks-without-approval/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `.apm/evals/autogenesis/fixtures/implement-blocks-without-approval/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/2026-10-08-add-retry-note.md`
- `.apm/evals/autogenesis/fixtures/implement-blocks-without-approval/reference/SKILL.md`
- `.apm/evals/autogenesis/fixtures/implement-blocks-without-approval/reference/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/ordinary-refactor-near-miss/negative.results.json`
- `.apm/evals/autogenesis/fixtures/ordinary-refactor-near-miss/negative/app/durations.py`
- `.apm/evals/autogenesis/fixtures/ordinary-refactor-near-miss/reference.results.json`
- `.apm/evals/autogenesis/fixtures/ordinary-refactor-near-miss/reference/app/durations.py`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative-heading.results.json`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative-heading/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-retry-backoff-guidance.md`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative-heading/SKILL.md`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative-heading/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative.results.json`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-retry-backoff-guidance.md`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative/SKILL.md`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/negative/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference-heading.results.json`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference-heading/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-retry-backoff-guidance.md`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference-heading/SKILL.md`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference-heading/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference.results.json`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-retry-backoff-guidance.md`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference/SKILL.md`
- `.apm/evals/autogenesis/fixtures/plan-has-genesis-artifacts/reference/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative.results.json`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative/SKILL.md`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative/references/atlas/README.md`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative/references/atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/negative/references/atlas/index.md`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference.results.json`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference/SKILL.md`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference/references/atlas/README.md`
- `.apm/evals/autogenesis/fixtures/plan-only-in-resolved-atlas/reference/references/atlas/index.md`
- `.apm/evals/autogenesis/fixtures/skill-change-should-trigger/negative.results.json`
- `.apm/evals/autogenesis/fixtures/skill-change-should-trigger/negative/SKILL.md`
- `.apm/evals/autogenesis/fixtures/skill-change-should-trigger/negative/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/skill-change-should-trigger/reference.results.json`
- `.apm/evals/autogenesis/fixtures/skill-change-should-trigger/reference/SKILL.md`
- `.apm/evals/autogenesis/fixtures/skill-change-should-trigger/reference/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/subjects/python-app/app/durations.py`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/SCHEMA.json`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/decisions/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/experiences/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/2026-10-08-add-retry-note.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/.atlas/example.invalid/fixtures/retry-helper-atlas/log.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/SKILL.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-designed/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/SCHEMA.json`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/decisions/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/experiences/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/.atlas/example.invalid/fixtures/retry-helper-atlas/log.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/SKILL.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/references/atlas/README.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-legacy/references/atlas/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-unmounted/SKILL.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject-unmounted/atlas-mesh.json`
- `.apm/evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/SCHEMA.json`
- `.apm/evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/decisions/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/experiences/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject/.atlas/example.invalid/fixtures/retry-helper-atlas/log.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject/SKILL.md`
- `.apm/evals/autogenesis/fixtures/subjects/subject/atlas-mesh.json`
- `.apm/evals/autogenesis/tasks/design-stops-for-approval.yaml`
- `.apm/evals/autogenesis/tasks/discussion-has-no-implement-authority.yaml`
- `.apm/evals/autogenesis/tasks/help-does-not-mount.yaml`
- `.apm/evals/autogenesis/tasks/implement-blocks-without-approval.yaml`
- `.apm/evals/autogenesis/tasks/ordinary-refactor-near-miss.yaml`
- `.apm/evals/autogenesis/tasks/plan-has-genesis-artifacts.yaml`
- `.apm/evals/autogenesis/tasks/plan-only-in-resolved-atlas.yaml`
- `.apm/evals/autogenesis/tasks/skill-change-should-trigger.yaml`
- `.github/ISSUE_TEMPLATE/bug_report.md`
- `.waza.yaml` (added 2026-10-08 02:16 BST approval: SKILL.md token budget 4000; `paths.evals: .apm/evals` added 07:10 BST)
- `AGENTS.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `SKILL.md`
- `apm.yml`
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
- `scripts/test_validate_consumer.py`
- `scripts/validate_consumer.py`

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

## Supplied run and suite fixes (suite_version 2)

Master of Trials ran the dogfood suite at f43df15 (suite_version 1) on
2026-10-08 with upstream Waza 0.38.9: 8 tasks, 3 trials each. The gate came
back red, but the run is **not valid evidence**:

- Contamination: Waza was started from the repository root. Waza's Copilot
  SDK engine adds its working directory to the agent's skill directories, so
  all 22 `autogenesis` invocations loaded the checkout's `SKILL.md`, not the
  installed copy, and in 7 of 24 trials the agent read suite files (task
  YAML, reference and negative fixtures, hand-authored results). The
  installed `autogenesis` copy also carried `evals/`, because APM 0.30.0
  copies every path of a root-`SKILL.md` package except `.apm/`.
- Environment: the image had no `python3`, so `atlas.py resolve` exited 127
  and one design trial failed closed.
- Suite defects: the `change_class:` pattern was stricter than the design
  rule ("State in the plan"); one trial wrote a `## Change class` heading and
  failed. `skill_invocation` scores F1, so passing runs that also loaded
  companion skills scored 0.33-0.5. The README's `paths.skills` advice
  recursed into modules and fixture `SKILL.md` folders and shadowed the
  `think-*` skills.

Sergio asked at 07:10 BST for fixes A-E on PR 25. Done through fresh Copilot
CLI sessions (commits 1858aed and 8f076d7):

- A: the class check accepts a `change_class:` / `change-class:` key or a
  "Change class" heading whose first non-blank line names `hardening`,
  `new-surface` or `new-skill`; new `reference-heading` (known-good) and
  `negative-heading` (known-bad, only the class check fails) fixtures and a
  source test that applies both patterns to the four plans.
- B: Waza 0.38.9 has no recall-only `skill_invocation` option (only
  `required_skills`, `forbidden_skills`, `mode`, `allow_extra`; score is
  always F1; `passed` does not depend on it). Graders unchanged; the README
  and guide tell runners to take verdicts from `passed` and read
  `details.recall` and `details.actual_skills`.
- C: README and guide recommend `config.skill_directories` in a local copy of
  `eval.yaml` instead of `paths.skills`.
- D: the suite moved to `.apm/evals/autogenesis/` (root `.waza.yaml` sets
  `paths.evals`); `diff` graders resolve from
  `.apm/evals/autogenesis/fixtures/subjects`; `scripts/validate_consumer.py`
  fails both CI consumer jobs if an installed skill carries `evals/`, `.apm/`
  or any `eval.yaml` (it fails on the f43df15 tree and passes on the new one
  with APM 0.30.0 locally; `apm lock` leaves the lock unchanged); a source
  test and the `suite-not-shipped` smoke check the layout. The README gives a
  run layout: `/suite` export, `/skills` holding only `.agents/skills/`,
  `/run` as the Waza working directory with only the subject skeletons,
  `$TMPDIR` for workspaces. The guide and the implement and
  workflow-discipline modules place a root-`SKILL.md` APM subject's suite at
  `<subject>/.apm/evals/<skill>/`.
- E: the README says the runner image needs `python3`. Master of Trials is
  building an approved runner image that includes it.

Model-free validity re-run offline at 8f076d7 (the same local Waza image as
before, network off, `WAZA_NO_UPDATE_CHECK=1`, Waza 0.38.9): V1 exit 0, eval found at
`.apm/evals/autogenesis/eval.yaml` via `paths.evals`, schema valid, skill
findings unchanged; V2 exit 0, 1 requirement, 0 covered; V3 reference 7/7
passed, negative 7/7 failed; `plan-has-genesis-artifacts` file grader (judge
removed in a throwaway copy): reference and reference-heading passed,
negative and negative-heading failed. Unit tests 62 OK; smokes show the same
20 pre-existing failures and no new ones. Not run against an agent.

## Outcome

Done on the branch: PR 25 open at 8f076d7, not merged, no release.
Behavioural status: authored; the one supplied run (f43df15, suite_version 1)
is invalid evidence and backs no claim. Re-run of suite_version 2 goes to
Master of Trials.
