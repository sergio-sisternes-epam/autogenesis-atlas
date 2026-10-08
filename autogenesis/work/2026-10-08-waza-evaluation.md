---
type: work
title: "Evolve Autogenesis evaluation from the Gherkin gate to authored Waza eval suites"
created: "2026-10-08"
updated: "2026-10-08"
work_id: "2026-10-08-waza-evaluation"
status: done
subject: autogenesis
plan_path: autogenesis/plans/2026-10-08-waza-evaluation.md
closes: []
scenario_ref: references/scenarios/waza-evaluation-adversarial-v1.yaml
evaluation_evidence: autogenesis/experiences/2026-10-08-waza-evaluation-implementation.md
external_ref: https://github.com/sergio-sisternes-epam/autogenesis/pull/25
eval_suite_ref: "evals/autogenesis/ @ 7d3ffc8985a159cf959bf09b88f49354565b5681 (suite_version 1)"
behavioural_status: authored-not-run
description: "Replaced the agent-spec/Gherkin behavioural-contract gate with upstream Waza eval suites that Autogenesis designs, authors and checks with model-free Waza commands but never runs (plan revision 3). Done on PR 25 (0.9.0, not merged, no release); the Autogenesis dogfood suite evals/autogenesis/ is authored-not-run and handed to Master of Trials."
origin: derived
sensitivity: internal
tags: [work, lineage, evaluation, waza]
relates_to:
  - path: autogenesis/experiences/2026-10-08-waza-evaluation-implementation.md
    kind: related
  - path: autogenesis/plans/2026-10-08-waza-evaluation.md
    kind: related
  - path: autogenesis/work/2026-09-11-remove-construct-binding.md
    kind: follows
  - path: autogenesis/work/2026-08-25-specify-only-behavioural-contract.md
    kind: related
---

# Work: 2026-10-08-waza-evaluation

## Scope

Sergio asked on 2026-10-08 (00:57 BST) to think how Autogenesis should
replace its Gherkin-based evaluation with Waza. The design covers authoring,
suite location, trials and pass bar, Exit evidence and receipts, CI and
token, harness neutrality, dependency stance, derived-skill stance and
migration phases. Design only; no package change.

## Status

done (2026-10-08): Phase 1 and Phase 2 implemented on PR 25 (head 7d3ffc8, CI green, not merged, no release). Model-free validity: reference 7/7 passed, negative 7/7 failed; plan-has-genesis-artifacts left to the runner. Not run against an agent.

implementing (2026-10-08 01:25 BST): Sergio approved Phase 1 and Phase 2.

designed (2026-10-08), revision 2. Sergio's feedback at 01:06 BST narrowed
the scope: Autogenesis designs and authors Waza evals but does not run them,
and depends only on upstream Waza. Revision 3 (01:10 BST): Sergio allowed
model-free validity checks (`waza check`, `waza spec verify` without
`--semantic`, update check off, Waza 0.38.9); deterministic graders are also
checked against authored fixtures with `waza grade`. Intended runner: a
separate on-demand evaluator bot. Plan stopped for approval. Approval would
authorise Phase 1 only (contract cutover, no model calls).

## Outcomes

- Implement experience: `autogenesis/experiences/2026-10-08-waza-evaluation-implementation.md` (PR 25).
- Plan: `autogenesis/plans/2026-10-08-waza-evaluation.md`, revision 3
  (change-class new-surface, 11 pins, revision-1 counters re-assessed plus
  new counters N1-N8, open question 1 closed, 8 remaining).
- Revision 1 (author and run) was superseded the same night by revision 2
  (author only).
- Inventory finding: there are no `.feature` files; agent-spec is undeclared
  and unavailable; 86 of 97 parsed current smokes assert instruction text;
  two scenario files are not valid YAML; CI never parses or runs scenarios.
- Implement experience: (pending)
- Evaluation evidence: (none yet)

## Related

Follows the 2026-09-11 removal of the private Construct evaluator. The same
reasoning backs the stance that upstream Waza is only the format target, with
no wrapper dependency.

## Status history

- designed: 2026-10-08 (revision 1)
- designed: 2026-10-08 (revision 2, author-only scope)
- designed: 2026-10-08 (revision 3, model-free validity checks allowed)
- approved: 2026-10-08 01:25 BST (Phase 1 and Phase 2)
- implementing: 2026-10-08
- done: 2026-10-08 (PR 25 open, not merged)
