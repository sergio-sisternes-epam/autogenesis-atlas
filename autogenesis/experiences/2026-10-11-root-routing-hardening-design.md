---
type: experience
title: "Designed root-routing hardening for discussion conclusions and forbidden plan paths"
created: "2026-10-11"
work_id: "2026-10-11-root-routing-hardening"
status: designed
description: "Design Run persisted a challenged hardening plan and stopped for approval. No product files were edited."
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-10-11-root-routing-hardening.md
    kind: implements
  - path: autogenesis/plans/2026-10-11-root-routing-hardening.md
    kind: records
  - path: autogenesis/decisions/block-discussion-to-implement.md
    kind: follows
---

## Context

Autogenesis v0.9.0 root routing did not tell the agent to start formal design
when a user asked to apply an agreed skill change, and it did not say that a
user-named plan path outside the resolved subject Atlas is a declined
override rather than a reason to stop. The subject store is
`github.com/sergio-sisternes-epam/autogenesis-atlas`, resolved from this
repository's single `atlas-mesh.json` store. The checkout was already present,
so the Run resolved it and did not fetch.

## What happened

The Run classified the work as hardening and loaded workflow-discipline,
design, the skill-design principles, the Waza authoring guide, the
think-challenge wrapper, and catalog think-challenge. Genesis was not in the
harness catalogue and is not an installed dependency, so the packet uses the
design module's abbreviated hardening depth.

Catalog think-challenge searches grounded the counters in the instruction
hierarchy (arXiv:2404.13208), over-refusal research (ACL 2026 LLM-VA), ITIL
change records, and HCI confirmation-dialog guidance. Owner rerun
`20261011T193509Z-autogenesis-24323b1` supplied the behavioural evidence:
task `discussion-has-no-implement-authority` trials 1 and 2 only refused;
task `plan-only-in-resolved-atlas` trial 3 resolved and then asked. This Run
did not execute that suite.

Pins keep the Discuss fence, start design instead of only refusing, name the
non-triggers, persist a declined plan path in the resolved store without
asking, and leave the legacy gitlink on migrate. The plan holds full
successor scenario drafts and optional additive Waza task drafts. It stops
for approval.

A later review of the same designed plan required three corrections, still
without implementation. Workflow-discipline step 6 is narrowed to the gitlink
migrate rule, so a plain directory or a user-named path is not a block once
resolution has succeeded. Successor smoke drafts search for plain backticks,
not backslash-backtick, and a design-time dry-run of those commands is
recorded in the plan. The just-discuss gate draft uses a zero-change
workspace allowlist, because the reused fixture already contains the plan and
work directories. Status remains designed.

## Outcome

Plan and work node are persisted at status designed. Review corrections are
in the same plan. No skill, scenario, eval, or changelog file was edited.
Implementation is blocked until explicit approval of
`autogenesis/plans/2026-10-11-root-routing-hardening.md`.

## Related

The plan records the proposed wording, pins, successor drafts, and open
questions.

## Follow-ups

Implement only after explicit approval. Do not treat this experience as
approval.
