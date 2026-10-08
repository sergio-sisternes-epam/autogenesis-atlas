---
type: work
title: "Evolve Autogenesis evaluation from the Gherkin gate to Waza skill evals"
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
description: "Design for replacing the agent-spec/Gherkin behavioural-contract gate with Waza task suites in the subject repo, 3 trials with pass^3 on gate tasks, cited at implement Exit. Status designed; Phase 1 awaits Sergio's approval."
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

designed (2026-10-08). Plan stopped for approval. Approval would authorise
Phase 1 only (contract cutover with no model calls). Phase 2 (supervised
pilot) is also blocked on a Copilot-only eval token decision.

## Outcomes

- Plan: `autogenesis/plans/2026-10-08-waza-evaluation.md` (change-class
  new-surface, 11 pins, 9 challenge counters, 13 open questions).
- Inventory finding: there are no `.feature` files; agent-spec is undeclared
  and unavailable; 86 of 97 parsed current smokes assert instruction text;
  two scenario files are not valid YAML; CI never parses or runs scenarios.
- Implement experience: (pending)
- Evaluation evidence: (none yet)

## Related

Follows the 2026-09-11 removal of the private Construct evaluator, whose
reasoning drives the stance that upstream Waza is an external tool and the
private waza-apm wrapper stays optional.

## Status history

- designed: 2026-10-08
