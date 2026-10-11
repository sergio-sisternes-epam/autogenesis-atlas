---
type: experience
title: "Implemented root-routing hardening for discussion conclusions and forbidden plan paths"
created: "2026-10-11"
work_id: "2026-10-11-root-routing-hardening"
implements: "2026-10-11-root-routing-hardening"
closes: "2026-10-11-root-routing-hardening"
plan_path: autogenesis/plans/2026-10-11-root-routing-hardening.md
status: done
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-10-11-root-routing-hardening.md
    kind: implements
  - path: autogenesis/plans/2026-10-11-root-routing-hardening.md
    kind: related
  - path: autogenesis/experiences/2026-10-11-root-routing-hardening-design.md
    kind: derived_from
---

## Context

Approved hardening of Autogenesis root routing, shipped in unreleased 0.9.0.
A discussion conclusion that changes a package starts formal design and stops
at status designed. Mere discussion, help, and ordinary application
refactoring do not start that design. A user-named plan path outside the
resolved subject Atlas is not a storage override: the Run persists in the
resolved store, says why the named path was not used, and does not stop to
ask. A legacy references/atlas gitlink still routes to migrate. A plain
directory does not block once resolution has succeeded.

Approval is `chat:2026-10-11T21:52Z:sergio`, quote "Approve the root-routing
hardening design with the recommended answers, in 0.9.0". The plan frontmatter
stays `approved`. That is the G4 record. This experience and the work node
record the implementation.

## What happened

Root `SKILL.md` and workflow-discipline now state both obligations. The
catalog description, help, and getting-started were not edited. Version
surfaces stay 0.9.0. Successors
`explicit-discuss-integration-adversarial-v2` and
`atlas-storage-semantics-adversarial-v5` were materialised from the approved
drafts. Predecessors were not edited. Dogfood `suite_version` moved from 14
to 15 by adding `just-discuss-does-not-start-design` and
`declined-plan-path-explained`. The evidence tasks
`discussion-has-no-implement-authority` and `plan-only-in-resolved-atlas`
were not modified.

The source-contract resource scanner treated the approved bare phrase
`references/atlas` in workflow-discipline as an unresolved module resource.
That path names the subject's legacy mount, not a module file. The scanner
now skips that exact token so the successor smoke can keep the approved
wording. Other bare `references/` tokens still fail.

The parent product commit is `243da8277d82f336d7ecb6b326a91800e13bcd03`.
The parent gitlink was left at `110cab3deb3a87695003c6276ad92426e6262521`.
Updating that pointer needs a separate review.

## Outcome

Routing prose matches the approved answers. Current scenario successors are
the two new files. The dogfood suite is authored at suite_version 15 and was
not run against a model.

## Changed files

- `.apm/evals/autogenesis/README.md` (updated)
- `.apm/evals/autogenesis/eval.yaml` (updated)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative.results.json` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/SCHEMA.json` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/decisions/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/experiences/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/2026-10-08-add-retry-note.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/log.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/SKILL.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/atlas-mesh.json` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/references/atlas/README.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/negative/references/atlas/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference.results.json` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/SCHEMA.json` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/decisions/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/experiences/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/2026-10-08-add-retry-note.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/log.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/SKILL.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/atlas-mesh.json` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/references/atlas/README.md` (created)
- `.apm/evals/autogenesis/fixtures/declined-plan-path-explained/reference/references/atlas/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative.results.json` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/SCHEMA.json` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/decisions/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/experiences/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/2026-10-08-add-retry-note.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/2026-10-08-add-retry-note.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/.atlas/example.invalid/fixtures/retry-helper-atlas/log.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/SKILL.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/negative/atlas-mesh.json` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference.results.json` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/SCHEMA.json` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/decisions/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/experiences/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/plans/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/autogenesis/work/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/index.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference/.atlas/example.invalid/fixtures/retry-helper-atlas/log.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference/SKILL.md` (created)
- `.apm/evals/autogenesis/fixtures/just-discuss-does-not-start-design/reference/atlas-mesh.json` (created)
- `.apm/evals/autogenesis/tasks/declined-plan-path-explained.yaml` (created)
- `.apm/evals/autogenesis/tasks/just-discuss-does-not-start-design.yaml` (created)
- `CHANGELOG.md` (updated)
- `SKILL.md` (updated)
- `references/modules/workflow-discipline/SKILL.md` (updated)
- `references/scenarios/atlas-storage-semantics-adversarial-v5.yaml` (created)
- `references/scenarios/explicit-discuss-integration-adversarial-v2.yaml` (created)
- `references/scenarios/suite-index.json` (updated)
- `scripts/test_source_contract.py` (updated)

## Evaluation evidence

Deterministic checks on the committed product tree. Python 3.13.5 was the
available interpreter; Python 3.12 was not installed.

- `python3 -m unittest discover -s scripts -p 'test_*.py'`: 94 tests, OK.
- `python3 scripts/release_readiness.py`: candidate_revision `243da8277d82f336d7ecb6b326a91800e13bcd03`, package_version 0.9.0, expected_tag v0.9.0, is_prerelease false, version_consistency pass, release_metadata_decision pass.
- `python3 scripts/dependency_contract.py`: dependency_contract pass, direct_dependencies 4, reviewed_anchor_divergences 0.
- `python3 scripts/audit_source.py --jobs 8`: source_audit_files 958, source_audit_failures 0, source_audit pass.
- `python3 scripts/store_contract.py`: exit 1 before this lineage commit. The checkout was `23d3a58e98c5600c41d24e1962b01889260c74f0` and the parent gitlink remained `110cab3deb3a87695003c6276ad92426e6262521`. This lineage commit advances the checkout further and does not update the parent gitlink, so the pointer check stays red. That update needs a separate review. Store compile is recorded separately.

Successor smokes, with the package root as the subject, all printed ok true:

- `explicit-discuss-integration-adversarial-v2`: 7 smokes, including `root-routing-starts-design`, `discuss-boundary-fence-retained`, and `non-triggers-and-authority-mirror`.
- `atlas-storage-semantics-adversarial-v5`: 12 smokes, including `declined-override-is-not-a-stop`, `legacy-gitlink-still-migrates`, and `release-surfaces-match-current-version` (expects 0.9.0).

The five new wording-dependent smokes printed `{"ok": false}` against a temporary copy of origin/main `SKILL.md` and workflow-discipline. Preserved smokes stayed green on this package.

```text
waza_suite:
  path: .apm/evals/autogenesis/ @ 243da8277d82f336d7ecb6b326a91800e13bcd03
  suite_version: 15
  format: waza 0.38.9, schemaVersion 1.4
  tasks: 10 (gate 7, quality 1, trigger 2)
  coverage: USE FOR 0/0, DO NOT USE FOR 0/0 (description has no such labels; spec verify reported 1 whole-description requirement, 0 covered)
  grader_controls: reference + negative fixture for 7/7 gate tasks
  validity:
    waza: 0.38.9
    env: WAZA_NO_UPDATE_CHECK=1
    check:
      cmd: WAZA_NO_UPDATE_CHECK=1 waza check . --format json
      exit_code: 0
      summary: eval found; schema.valid true; ready false; SKILL.md 4169 tokens against the project budget of 4000 (exceeded, budget not raised); compliance Medium
    spec_verify:
      cmd: WAZA_NO_UPDATE_CHECK=1 waza spec verify --skill . --eval .apm/evals/autogenesis/eval.yaml --format json
      exit_code: 0
      coverage: 1 requirement, 0 covered deterministically; semantic false; no --fail and no judge model
    grader_fixtures:
      cmd: WAZA_NO_UPDATE_CHECK=1 waza grade .apm/evals/autogenesis/eval.yaml --task <id> --results fixtures/<id>/<variant>.results.json --workspace fixtures/<id>/<variant>/
      checked: 9 deterministic tasks, 52 fixture variants; reference passed 12/12, negative failed 40/40; every grade call exited 0
      left_to_runner: plan-has-genesis-artifacts
    output_log: grade summaries recorded in this experience; not stored as a product file
  run_status: not-run-by-autogenesis
```

`declined-plan-path-explained` negative failed only `named_path_explained`
(score 0.5: the resolved-path regex matched and the statement that the named
path was not used did not). File and allowlist graders scored 1 on that
negative. `just-discuss-does-not-start-design` reference passed the
zero-change allowlist; its negative failed only that allowlist.

This block is not behavioural evidence. No suite task was run against a model.
