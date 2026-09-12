---
type: plan
title: Isolate later SOLID implement from Autogenesis PR 15
created: 2026-09-12
work_id: 2026-09-12-isolate-pr15-gitlink
status: designed
change_class: hardening
subject: autogenesis
description: Operator-owned draft PR 15 stays the dogfood first slice. Later SOLID implement must not rewrite that branch or silently retarget gitlink 6746d60.
relates_to:
  - path: autogenesis/work/2026-09-12-isolate-pr15-gitlink.md
    kind: implements
  - path: autogenesis/work/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: follows
  - path: autogenesis/plans/2026-09-12-thin-root-router.md
    kind: related
  - path: autogenesis/plans/2026-09-12-invocation-json-checker-policy.md
    kind: related
---

# Isolate later SOLID implement from Autogenesis PR 15

**Stops for approval. Do not implement product files.**

`change_class: hardening`

## Intent + scope

sergio-sisternes-epam/autogenesis#15 (`6746d609f3bcfe91f59d783c29a14b362629b642`)
is the approved dogfood first slice. This work records the isolation contract
for thin-root and JSON-policy implement: new branch from GitHub default main
after #15 merges, or a stacked branch only if the operator explicitly asks.
Atlas memories for those designs live on
`2026-09-12-solid-architecture-review` / Atlas PR
sergio-sisternes-epam/autogenesis-atlas#11, not on the #15 gitlink.

No Autogenesis product file changes in this work.

## Non-goals

- Review, merge, rebase, or force-push #15 except at operator request.
- Advance `scripts/store_contract.py` STORE_COMMIT as part of this isolation
  record.
- Implement thin-root or JSON-policy here.

## Pins

1. **#15 gitlink frozen for this lineage** until a later governed pin on a
   different Autogenesis PR.
2. **Atlas PR #11 stays open** until the operator wants it merged.
3. **think-* untouched** (separate catalog-think work already shipped).

## SOLID record (abbreviated)

| Principle | Status | Rationale / design consequence |
|---|---|---|
| S | applicable | Dogfood evidence and architecture follow-ons have different reasons to change. |
| O | applicable | Do not silently drift the reviewed store pin. |
| L | not-applicable | PR branches are not interchangeable substitutes. |
| I | not-applicable | No caller interface change. |
| D | not-applicable | No dependency abstraction. |

Omitted principles are not material beyond the table: this is change-set
hygiene, not a skill-surface redesign.

## Genesis Artifacts

### Intent + scope + acceptance

- Later implement PRs do not list #15 as their head.
- Atlas remember for thin-root/JSON work does not require moving #15's
  gitlink.
- Operator retains merge of #15.

## Catalogue Review

n/a — change-set isolation, not topology, gates, or pattern injection.

## Behavioural contract (agent-spec)

deferred: no skill behaviour change.

## Evaluation plan

n/a for product behaviour. Process check: implement receipts for the sibling
works must name a branch other than
`sergio-sisternes-epam-solid-dogfood-implement` unless the operator
explicitly stacks.

## Challenge

| Counter | Source | Severity | Pin |
|---|---|---|---|
| Leaving #15 open forever blocks store_contract on later work | store pin | medium | Governed pin only on the later PR after #15 merges or operator directs |
| Rebase-onto-main of #15 is still allowed | operator | low | Operator-requested rebase is in scope; silent retarget is not |

## Stop for approval

Explicit user approval required before treating this isolation as binding
implement policy. No product implement exists in this work.
