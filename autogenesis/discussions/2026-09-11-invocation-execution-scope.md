---
type: document
title: Invocation remains an instruction-based protocol
created: 2026-09-11
status: settled
kva: alive
stage: discussion
artifact: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
relates_to:
  - path: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
    kind: derived_from
---

# Execution scope

## Discussion

The alternative was a new executable invocation engine. The recommendation was
to preserve the skill-package model: agents follow the protocol using existing
harness tools, with targeted conformance checks. The function analogy alone
does not require a dispatcher, call-stack implementation, or new runtime.

## Decision

On 2026-09-11 the user selected:

> Instruction-based protocol with targeted conformance checks (Recommended)

The first evolution does not build a new execution engine. Deterministic checks
may validate structural contracts, while agent adherence is not misrepresented
as machine-enforced execution or authorisation.

## Process agreement

The user requested one question at a time and durable memory of all discussions
and decisions. Resolve the remaining branches sequentially, then produce a
formal design for explicit approval. This concept approval is not approval
to implement a migration.
