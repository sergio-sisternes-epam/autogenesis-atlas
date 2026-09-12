---
type: document
title: Full operation cards and compact supporting cards
created: 2026-09-11
status: settled
kva: alive
stage: discussion
artifact: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
relates_to:
  - path: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
    kind: derived_from
---

# Presentation policy

## Discussion

The approved card concept is a visible interface and cue for an invocation
request. The agent contrasted full cards for every request with full root
and operation cards plus compact supporting cards.

The proposed compact form identifies the module, caller, and request without
repeating all inherited context. Existing mandatory output contracts remain
supported during migration.

## Decision

On 2026-09-11 the user selected:

> Compact visible cards for support requests; full cards for root and operation requests (Recommended)

When cards are enabled, support requests remain visible; compact does not mean
silent. Root-skill and operation requests use full cards. Preserve existing
off/on/debug semantics and do not render secrets merely because the request
contains them.

Formal design must reconcile compact cues with existing required card fields
and identify the full request context they refer to. Exact formatting and
correlation field names are not yet selected. A cue signifies a request, not
execution success or authorisation.
