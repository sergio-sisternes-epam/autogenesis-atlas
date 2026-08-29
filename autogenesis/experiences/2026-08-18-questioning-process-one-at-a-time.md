---
type: experience
title: "Questioning process that worked: one problem at a time, one question at a time"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "User explicitly liked the structured questioning used while discussing the six agent-brain test problems. Capture the pattern and a pending improvement for future Autogenesis discussions."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-questioning-process-one-at-a-time`.

## What happened

During the discussion of the six problems surfaced by the agent-brain v0.1 Terraform test, the following discipline was used:

- One problem at a time.
- Inside each problem, one question at a time.
- Lock the answer before moving to the next question or problem.
- At the end, synthesise all locked decisions into a single coherent plan.

User feedback (verbatim tone): “I like how you structured this questioning process.”

## Why it worked
- Prevented context overload.
- Forced clear, atomic decisions.
- Made it easy to lock each point without revisiting earlier ones.
- Produced a clean synthesis that could be turned directly into a refinement plan.

## Pending improvement (follow-up)

Recorded so future Autogenesis discussion / grill / design paths can improve:

- When a multi-problem discussion is expected, proactively offer the “one problem at a time / one question at a time” mode at the start instead of waiting for the user to request it.
- Consider a lightweight “discussion card” that states the current problem number and question number so both sides always know where they are.
- After the final synthesis, always ask whether the user wants the decisions turned into a formal plan immediately (as done here).

This is a process improvement for Autogenesis itself, not for agent-brain.

## Related
- The six locked decisions are being turned into an agent-brain refinement plan in the same session.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
