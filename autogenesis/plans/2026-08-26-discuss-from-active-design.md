---
type: plan
title: "Hardening — discuss from an active design"
created: "2026-08-26"
work_id: "2026-08-26-discuss-from-active-design"
status: approved
change_class: hardening
subject: autogenesis
description: "Design-review problem re-enters path discuss on the same work; reuse discussion_root; prior nodes in scope."
relates_to:
  - path: autogenesis/work/2026-08-26-discuss-from-active-design.md
    kind: implements
  - path: autogenesis/work/2026-08-26-autogenesis-discuss-activation.md
    kind: related
---

## Intent + scope

Document and enforce: a problem found while reviewing a design opens path discuss by re-issuing Enter. Same work_id. stage design. artifact is the plan. Existing discussion_root reused. Prior idea nodes in scope.

## Non-goals

Nested paths. New catalog behaviour. Typed cross-Atlas edges.

## Pins

Reuse root. Move current_branch. Query prior nodes. Re-enter design after pin/defer. No discussion to implement.

## Genesis Artifacts

### Intent + scope + non-goals

Hardening: intent, acceptance, pins only.

### Cost note

No extra skill load beyond a normal discuss Enter.

## Acceptance

Path discuss and workflow-discipline contain the from-active-design rule. v1 adversarial smokes kept in v2. Version 0.3.12.

## Stop for approval

User requested implement of this enhancement directly.
