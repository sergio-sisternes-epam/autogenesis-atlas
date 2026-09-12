---
type: plan
title: Thin Autogenesis root SKILL.md into a router
created: 2026-09-12
work_id: 2026-09-12-thin-root-router
status: designed
change_class: hardening
subject: autogenesis
description: Relocate duplicated Atlas, approval, and substrate prose from root SKILL.md into workflow-discipline. Keep think-* wrappers. No new module.
relates_to:
  - path: autogenesis/work/2026-09-12-thin-root-router.md
    kind: implements
  - path: autogenesis/plans/2026-09-12-14-root-prose-dedupe.md
    kind: derived_from
  - path: autogenesis/plans/2026-09-12-solid-architecture-review.md
    kind: follows
  - path: autogenesis/plans/2026-09-12-isolate-pr15-gitlink.md
    kind: related
---

# Thin Autogenesis root SKILL.md into a router

**Stops for approval. Do not implement.**

`change_class: hardening`

## Intent + scope

Root SKILL.md currently repeats Atlas write-home, approval, discuss boundary,
and substrate-contract rules that workflow-discipline already owns. After
approval, implement relocates that duplicated authority into
`references/modules/workflow-discipline/SKILL.md` and leaves the root as
version surface, module registry, and load-before-follow router.

Absorbs protostar `autogenesis/plans/2026-09-12-14-root-prose-dedupe.md`.

## Non-goals

- Fuse, delete, or rewrite `think-challenge`, `think-grill`, or `think-ramble`
  (catalog `think@atlas` nest-load wrappers).
- Add a module, adapter, runtime schema, validator, or Python script.
- Modify Genesis, B17, or S8 admission.
- Mutate sergio-sisternes-epam/autogenesis#15 or retarget gitlink `6746d60`.

## Pins

1. **One process authority.** workflow-discipline owns G0–G8 and invocation.
2. **Root stays catalogue identity.** Registry table remains on the root.
3. **think-* untouched.**
4. **PR #15 isolation.** New parent branch after approval.

## SOLID record

| Principle | Status | Rationale / design consequence |
|---|---|---|
| S | applicable | Root reason-to-change is routing; discipline reason-to-change is process. Relocate prose (`keep` discipline). |
| O | applicable | Parent-owned context semantics stay closed; this is governed copy move, not a new extension point. |
| L | not-applicable | Root and discipline do not claim interchangeability. |
| I | applicable | Callers of an operation should not reload full write-home essays from the root. |
| D | not-applicable | No new dependency; Atlas remains a concrete external skill. |

## Genesis Artifacts

### Intent + scope + non-goals

Covered above.

### Acceptance

- Root SKILL.md still lists the 20-module registry and points to
  workflow-discipline as the sole process authority.
- Duplicated Atlas/approval/substrate paragraphs are not restated at length
  on the root.
- Existing source-contract tests pass without a new Python file.
- think-* entrypoints unchanged.

## Catalogue Review

- genesis matches: none (no panel/fan-out change)
- Autogenesis extension: B17 remains active for request cards; S8
  `pattern_applicability: applicable` for Autogenesis itself,
  `pattern_admission: draft` unchanged
- composition: INLINE duplicated prose into existing support module
- inherited anti-patterns: do not invent a 21st module for “router”
- delta only: copy locality
- admission note: draft S8 is not promoted

## Behavioural contract (agent-spec)

deferred: agent-spec is not an Autogenesis runtime dependency; portable
scenario smokes plus source-contract tests are the evaluation surface.

## Evaluation plan

Deterministic: existing `scripts/test_source_contract.py` plus a smoke
`root-is-router-not-process-authority` added to a current-suite YAML by
extending existing files only. Agent narrative is secondary.

## Challenge

| Counter | Source | Severity | Pin |
|---|---|---|---|
| Thinning the root hides required Atlas rules from agents that only read SKILL.md | progressive disclosure / I | high | Keep a one-line pointer and load-before-follow; do not delete the rules |
| Agents skip workflow-discipline after thinning | G1 | high | Bootstrap still requires reading workflow-discipline |
| Mixing this into PR #15 | change-set isolation | high | Separate branch; see isolate-pr15 plan |

Adversarial draft filename:
`references/scenarios/thin-root-router-adversarial-v1.yaml`
smokes: `root-is-router-not-process-authority`, `think-modules-untouched`,
`no-new-runtime-module` (source: this plan).

## Stop for approval

Explicit user approval required before implement.
