---
type: experience
title: Implementing the Parent-routed Skill Module draft pattern
created: 2026-09-11
work_id: 2026-09-11-parent-routed-skill-module-pattern
implements: 2026-09-11-parent-routed-skill-module-pattern
closes: []
plan_path: autogenesis/plans/2026-09-11-parent-routed-skill-module-pattern.md
construct_eval: deferred
status: deferred
subject: autogenesis
origin: internal
sensitivity: internal
description: Approved S8 draft implemented locally with admission and boundary checks; final CI and live behavioural acceptance remain pending.
relates_to:
  - path: autogenesis/work/2026-09-11-parent-routed-skill-module-pattern.md
    kind: implements
  - path: autogenesis/plans/2026-09-11-parent-routed-skill-module-pattern.md
    kind: records
  - path: autogenesis/experiences/2026-09-11-skill-module-pattern-design.md
    kind: follows
  - path: autogenesis/experiences/2026-09-11-module-invocation-implementation.md
    kind: related
---

# S8 draft implementation

## Approval and scope

The user said "Approved" at 15:05 +01:00 on 2026-09-11 while the persisted
S8 design packet was active. Applied that packet directly, without additional
agents. This approval permits draft implementation, not active admission,
publication, global installation or release.

Added `autogenesis:S8`, stable resource `parent-routed-skill-module`, as a
passive structural pattern asset. Genesis's distribution-module ontology
remains distinct from the private skill module. B17 remains active; no new
runtime module, schema authority, dependency or catalogue export was added.

The injector and design/initialise/review-package callers now expose applicable
draft selection and admission notes. The existing initialise fusion and
implementation approval gates remain intact. Root registry descriptions were
aligned as required by the root's same-change registry rule.

Known-use recording accepts the selected pattern, retains B17 as the existing
default and rejects unknown selections. Draft use never promotes admission.
The existing 21-leaf migration is recorded as one experimental application.

## Integration choices and corrections

- The extension index has an active subsection and a draft subsection.
  "Sole remaining pattern" is explicitly qualified "in active status": B17 is
  still the only active extension. This preserves the existing scenario
  assertion truthfully, without hiding S8 or changing any prior YAML body.
- Existing Load and default B17 known-use wording is retained and extended
  with draft discovery and explicit selected-pattern recording.
- Three new regression methods exercise valid source and targeted negative
  mutations: premature admission/upstream identity, B17 deprecation, lost
  context boundary, copied schema, missing asset, caller selection notes and
  simple/independent-release near-miss guidance.
- Initial checks exposed an incorrect heading-helper argument and a fixture
  that rewrote design without its new selection notes. Corrected both; negative
  tests now start from a passing fixture and assert the intended diagnostic.
- The pattern is 575 whitespace-delimited words. This is a size observation,
  not an exact tokenizer count or a measured token/cost saving.

## Local evidence

| Evidence | Actual result |
|---|---|
| Original baseline | 68 tests passed before source edits |
| Integrated Python 3.12.13 suite | 71 tests passed |
| Source contract | 21 modules, 21 entrypoints, 21 registry rows, 25 scenarios; no errors or warnings |
| Scenario inventory | 13 current, 12 historical; nine successor mappings preserved |
| Existing scenario bodies | SHA-256 comparison passed for all 23 pre-existing YAMLs |
| Release/dependency/store contracts | Passed; package remains 0.5.0; reviewed gitlink unchanged |
| APM source audit | 51 tracked source files passed; every new untracked source file explicitly audited |
| APM 0.30.0 agent-skills consumer | Install, complete owned assets, frozen replay and audit passed |
| APM 0.30.0 stable-runtimes consumer | Same checks passed for all nine target deployments |
| Protected surfaces | Lock, mesh, gitmodules and CI workflow diff remained empty |
| Whitespace | git diff --check passed |

Retained session evidence lives in session
`aa9a2f4d-9638-4c14-a557-c1cf6a900529/files/final-local-ZFSzi8/`:
`s8-agent-skills.log`, `s8-stable-runtimes.log`, `s8-tracked-audit.log`,
`s8-new-audit.log`. The sibling `s8-baseline-scenario-hashes.txt` records the
pre-edit scenario hashes. The earlier original-cutover logs were not replaced.

Both consumer runs used the existing isolated HOME/APM configuration and
ordinary read-only gh authentication, without exposing credentials or
altering global consumers. Genesis and installed skills were read-only.
No staging, commits, pushes, tags or releases were performed.

## Acceptance boundary

defer: Final GitHub CI, Construct execution and paired live design/selection evaluations remain pending; Construct still fails with ModuleNotFoundError: No module named 'construct'.

Re-ran `construct --help` and observed that failure. No replacement dependency
source/version was justified or installed. The two new approved scenario
drafts are materialised, and their referenced unit/source commands passed,
but this is not a Construct report or live behavioural proof.

The three paired tasks, disposable real design exercise and 20 selection
queries have not been executed. No recall/false-positive scores, savings,
new actual host-discovery claims or active admission are asserted. Structural
assertions do not prove that an agent makes the intended selection.

This work remains deferred for final acceptance. It does not close the earlier
module-invocation cutover or waive any of its remaining gates.

## Changed files

Every product file created or edited in this S8 implementation:

- `SKILL.md`
- `AGENTS.md`
- `README.md`
- `CONTRIBUTING.md`
- `CHANGELOG.md`
- `references/modules/patterns/references/parent-routed-skill-module.md`
- `references/modules/patterns/SKILL.md`
- `references/modules/design/SKILL.md`
- `references/modules/initialise/SKILL.md`
- `references/modules/review-package/SKILL.md`
- `scripts/module_contract.py`
- `scripts/test_module_contract.py`
- `scripts/test_source_contract.py`
- `references/scenarios/suite-index.json`
- `references/scenarios/skill-module-pattern-adversarial-v1.yaml`
- `references/scenarios/skill-module-pattern-happy-v1.yaml`

Subject-memory updates also record approval in the plan/design experience,
link this experience from its work hub and index, and align plan/work index
status. No work closure or structural store migration occurred.
