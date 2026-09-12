---
type: document
title: Bounded safe retries within the calling operation
created: 2026-09-11
status: settled
kva: alive
stage: discussion
artifact: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
relates_to:
  - path: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
    kind: derived_from
---

# Invocation lifecycle

Define caller/child relationships, return to the active operation, and the
meaning of rejected, blocked, failed, completed, or paused work. Determine
what correlation evidence is needed to distinguish repeated requests.

Recommended direction: preserve one active operation while support invocations
return to it; keep external skills on their own contracts; propagate failures
explicitly. Do not auto-retry work that may have side effects or treat a loaded
module as already executed for a later request. Full concurrency, recursive
composition, and a new scheduling engine are not assumed requirements.

## Discussion and user selection

The agent offered stopping dependent work without retry, bounded automatic
retry, or a parent-selected fallback. On 2026-09-11 the user selected:

> Attempt a bounded automatic retry before reporting failure

Bounded retry is therefore the chosen direction, rather than the agent's
initial no-automatic-retry recommendation. The subsequent decisions below
settle retry eligibility and the bound.

## Retry eligibility decision

A transient failure may be recoverable, but a partially completed write may
not be safe to repeat. Missing approval, invalid input, and policy denial are
not transient failures.

On 2026-09-11 the user selected:

> Only transient failures where repeating the work is known to be safe (Recommended)

Automatic retry must not replay an uncertain side effect or bypass approval,
permissions, or input validation. Unknown repeat safety means no automatic
retry.

## Retry bound decision

On 2026-09-11 the user selected:

> One retry: two attempts total (Recommended)

The initial attempt plus at most one eligible retry is the complete automatic
budget. If the retry fails, report the failure and stop dependent work.
Changing module aliases or re-entering a helper must not silently reset this
budget for the same request.

Formal design will specify request/attempt correlation and receipt fields.
Support calls preserve the active operation; external skills keep their own
contracts. No new scheduler or general-purpose recovery engine is implied.
