---
type: document
title: Parent owns protected invocation context
created: 2026-09-11
status: settled
kva: alive
stage: discussion
artifact: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
relates_to:
  - path: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
    kind: derived_from
---

# Request contract

## Discussion

Separate task-specific arguments from inherited execution context and
loader-resolved metadata. Alternatives were selected context overrides or
each module constructing its own context.

The recommendation was that callers supply an objective or target artifact,
while the parent owns the active subject, mode, Atlas, work identity, and
approval context. Modules cannot override those values to gain authority.

## Decision

On 2026-09-11 the user selected:

> Parent owns protected context; callers supply task-specific arguments (Recommended)

The parent or loader resolves the entrypoint. Modules may specialise their
task inputs but cannot broaden authority. Approval evidence must be validated
rather than accepted from an input boolean. Legitimate context changes require
the parent's existing transition discipline, not module-local overrides.

Exact required fields, invalid/conflicting-input handling, and schema layout
will be made explicit in formal design under this ownership rule.
