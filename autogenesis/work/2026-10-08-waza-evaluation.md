---
type: work
title: "Evolve Autogenesis evaluation from the Gherkin gate to authored Waza eval suites"
created: "2026-10-08"
updated: "2026-10-08"
work_id: "2026-10-08-waza-evaluation"
status: designed
subject: autogenesis
plan_path: autogenesis/plans/2026-10-08-waza-evaluation.md
closes: []
scenario_ref: null
evaluation_evidence: null
external_ref: null
eval_suite_ref: null
behavioural_status: null
description: "Design (revision 2) for replacing the agent-spec/Gherkin behavioural-contract gate with Waza eval suites that Autogenesis designs and authors but never runs. Running belongs to the subject owner; supplied results may be cited with provenance. Status designed; Phase 1 awaits Sergio's approval."
origin: derived
sensitivity: internal
tags: [work, lineage, evaluation, waza]
relates_to:
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

designed (2026-10-08), revision 2. Sergio's feedback at 01:06 BST narrowed
the scope: Autogenesis designs and authors Waza evals but does not run them,
and depends only on upstream Waza. Plan stopped for approval. Approval would
authorise Phase 1 only (contract cutover, no model calls).

## Outcomes

- Plan: `autogenesis/plans/2026-10-08-waza-evaluation.md`, revision 2
  (change-class new-surface, 11 pins, revision-1 counters re-assessed plus
  new counters N1-N5, 9 open questions).
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
