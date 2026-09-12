---
type: experience
title: Applying instruction-first guidance to derived skills
created: 2026-09-11
work_id: 2026-09-11-instruction-first-skill-modules
implements: 2026-09-11-instruction-first-skill-modules
closes: []
plan_path: autogenesis/plans/2026-09-11-instruction-first-skill-modules.md
construct_eval: deferred
status: probed
origin: internal
sensitivity: internal
description: Implemented the approved lightweight derived-skill discipline; bounded walkthroughs succeeded, while independent evaluation and release acceptance remain deferred.
relates_to:
  - path: autogenesis/work/2026-09-11-instruction-first-skill-modules.md
    kind: implements
  - path: autogenesis/plans/2026-09-11-instruction-first-skill-modules.md
    kind: records
  - path: autogenesis/experiences/2026-09-11-python-tooling-overengineering-challenge.md
    kind: follows
  - path: autogenesis/experiences/2026-09-11-module-migration-release-review.md
    kind: related
---

# Applying instruction-first guidance to derived skills

## Approval and scope

The user explicitly selected **Approve implementation** for the replacement
formal design. Implementation followed that approved plan, not the earlier
deferred core/profile proposal.

At 2026-09-11T18:21:20+01:00 the user reiterated **Approved. Proceed with
implementation**. The already-present source implementation was therefore
carried through the remaining local release checks without treating that
approval as a waiver of acceptance gates.

The central distinction is preserved: Autogenesis's authoring process,
generated skills' runtime, and repository release tooling are separate.
Nothing here deletes the repository release scripts or automatically changes
existing derived skills. No new machine profile, interpreter or validator
was introduced.

## Changes

- S8 is now draft version 0.2: useful instructions, private parent routing,
  explicit inputs/boundaries/outcomes and optional local resources. The small
  module template is passive authoring material, not another module export.
- Design and initialise select runtime capabilities by purpose. Root-only
  skills are valid; no default workflow module, design operation, protocol
  schema or runtime Atlas is inherited. Explicit full fusion remains possible.
- B17 remains active. Its portable request cue is distinguished from the
  Autogenesis-specific full/compact receipts, retries and memory application.
- Generic review applies the target's actual architecture and integrations.
  No declared OKF/Atlas means n/a; a declared broken integration is still a
  gap. Read-only target inspection cannot overwrite the author's write-home
  or mount/repair a target store.
- Autogenesis retains its own 21 modules and unchanged v1 JSON protocol.
  Existing source checks received only the new scenario inventory and one
  small template regression. The release candidate remains v0.5.0.

## Observed evidence

Evidence directory, relative to the session's persistent `files/`:
`instruction-first-eval/`.

| Check | Actual result and scope |
|---|---|
| Python 3.12 repository suite | 72 tests passed; pre-change baseline was 71 |
| Final targeted source/pattern checks | 14 passed after the final wording refinements |
| Final source inventory | 21 modules/registry entries; 26 suites, including 14 current and 12 historical |
| Release metadata | v0.5.0 consistency and release metadata decision passed |
| Dependency contract | Four direct dependencies, zero reviewed anchor divergences |
| Store contract | Reviewed store and pinned Atlas CLI contracts passed |
| Source audit | 51 files audited, zero failures; `final-source-audit.log` |
| Actual APM 0.30.0 consumers | Agent Skills and all nine stable runtimes passed install, owned-content validation, frozen replay and audit; `final-consumers.log` |
| New committed adversarial smokes | All four executed successfully against real walkthrough fixture files; `walkthrough-smokes.json` |
| Actual outputs | Plain text and approved-branch rewritten text matched independently specified expected files; shell script produced the expected CSV |
| Mutation boundary | Original fixture inputs remained byte-identical; no rewrite file existed at the unapproved walkthrough checkpoint |
| Protected release inputs | Root lock SHA256 remains `671d46bdda0f2c6192c3b0b446677f069620e03209de29a1fdefe3ddf2538bdc`; reviewed store gitlink remains `56d81a3034b2454520bcc6461a4ff4402a9ba0df` |

These source/deployment checks do not prove agent behavior. The walkthrough
used actual files and tool execution, but its guided skills were authored
and followed by the implementing agent. The approved rewrite branch used
simulated fixture approval; it is not evidence of an independent live
approval gate. No custom runtime trace infrastructure was needed.

### Independent evaluation attempt and refinement

The existing Copilot CLI was tried with GPT-5.4-mini at low effort, isolated
HOME directories, no custom instructions, no built-in MCP servers and a
restricted tool set. A readiness probe and one no-guidance text-editing task
completed. Five other launches were killed with signal 9 / exit 137 before
producing logs. Both sequential and standalone retries were attempted; the
cause was not established. Do not attribute this to the model or S8.

The completed baseline corrected the actual text, but its SKILL.md omitted
required name/description frontmatter. This observed task failure prompted
a small real-task refinement: initialise now explicitly retains that
frontmatter even when the output is root-only.

The guided three-case walkthrough then demonstrated a root-only skill,
private analyse/rewrite modules without framework files, and an explicitly
requested task-serving shell script. It is **not** a completed paired
comparison. No quantified benefit, saving, independent adoption, or active
pattern admission is claimed.

## Deferred acceptance

- **Construct:** the installed entrypoint raises
  `ModuleNotFoundError: No module named 'construct'`. No Construct report
  exists; the approved equivalent bounded smokes were run directly instead.
- **Independent live evaluation:** complete the three paired content tasks
  and the original fixed 20-query selection corpus with its 60/40 split when
  the evaluator can run reliably. Approval ordering, selection/load behavior,
  reviewer effort and comparative value remain unproven. The existing corpus
  and its baseline were not rewritten.
- **Release acceptance:** GitHub CI remains the final gate. No push, release,
  tag operation, repository setting change or global consumer update occurred.
- **Separate release blocker:** the ownership-ledger traversal defect in
  `validate_consumer.py` from the previous panel review is unchanged and
  outside this approved scope.

The instruction changes are present locally, but the work stays **deferred**
for acceptance rather than claiming a fully completed implementation Run.
S8 stays draft; the previous machinery-heavy plan remains historical.

## Changed files

Product paths relative to the Autogenesis repository. Earlier uncommitted
migration work is preserved; this list records files touched in this Run.

```text
AGENTS.md (updated)
CHANGELOG.md (updated)
CONTRIBUTING.md (updated)
README.md (updated)
SKILL.md (updated)
references/README.md (updated)
references/activation-plan-template.md (updated)
references/run-record-template.md (updated)
references/templates/work-node.md (updated)
references/modules/design/SKILL.md (updated)
references/modules/initialise/SKILL.md (updated)
references/modules/patterns/SKILL.md (updated)
references/modules/patterns/references/activation-card.md (updated)
references/modules/patterns/references/parent-routed-skill-module.md (updated)
references/modules/patterns/references/skill-module-template.md (created)
references/modules/review-package/SKILL.md (updated)
references/modules/validate-gate-map-and-non-goals/SKILL.md (updated)
references/modules/validate-okf-conformance/SKILL.md (updated)
references/modules/validate-progressive-disclosure/SKILL.md (updated)
references/modules/validate-skill-import-links/SKILL.md (updated)
references/modules/workflow-discipline/SKILL.md (updated)
references/modules/workflow-discipline/references/invocation-contract.md (updated)
references/scenarios/derived-skill-modules-adversarial-v1.yaml (created)
references/scenarios/suite-index.json (updated)
scripts/module_contract.py (scenario inventory updated)
scripts/test_module_contract.py (inventory expectations updated)
scripts/test_source_contract.py (inventory and optional-template regression updated)
```

## Memory and local artifacts

The current plan records explicit approval. Its work hub links this experience
and records the acceptance deferral; the plan/work/experience indexes are
aligned. Atlas mutations stay in this subject store.

Evaluation prompts, inputs, generated/walkthrough skills, outputs and CLI
logs remain under session `files/instruction-first-eval/`, not in the package.
Disposable tool homes/caches can be removed without removing that evidence.

## Exit

Installed Autogenesis v0.4.3 drove this Run without updating global consumers.
Its implement and workflow modules were loaded, as were Atlas mount, query,
remember/work and OKF authority. Actual Atlas resolve/search preceded the
completion memory. Final store compilation is recorded separately in
`files/instruction-first-eval/atlas-compile.log`.

`construct_eval: deferred`; no Construct success or fully accepted Run is
claimed. No product or Atlas commits were created.

## Superseding status note

The later approved evaluator-decoupling work removed Construct from the live
Autogenesis runtime and implementation gates. The failed attempt and deferral
above remain accurate historical evidence; they are no longer blockers for the
instruction-first implementation. Local completion evidence is recorded in
[Decoupling Autogenesis from the unavailable private evaluator](2026-09-11-evaluator-decoupling-implementation.md).
GitHub CI remains the final release gate, and S8 remains draft pending repeated
observed use and a separate admission decision.
