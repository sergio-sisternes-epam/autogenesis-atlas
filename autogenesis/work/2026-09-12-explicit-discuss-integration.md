---
type: work
title: "Replace Autogenesis embedded Discuss adapter with explicit package integration"
created: "2026-09-12"
work_id: "2026-09-12-explicit-discuss-integration"
status: done
description: "Autogenesis now uses the explicit direct Discuss package integration; the embedded adapter is removed."
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/plans/2026-09-12-explicit-discuss-integration.md
    kind: related
  - path: autogenesis/work/2026-08-26-autogenesis-discuss-activation.md
    kind: follows
---

## Scope

Replace Autogenesis's `path: discuss` adapter and its associated
discussion-mode routing with an explicit, documented dependency on the
catalogued `discuss@atlas` package. Discuss owns durable discussion behaviour;
Autogenesis remains the formal design and implementation discipline.

## Status

done - the user explicitly waived agent-spec `specify`. The embedded adapter
was removed, deterministic integration checks pass, and Construct evaluation
is deferred because its installed executable cannot import its Python module.

## Outcomes

- Plan: `autogenesis/plans/2026-09-12-explicit-discuss-integration.md`
- Predecessor: `autogenesis/work/2026-08-26-autogenesis-discuss-activation.md`
- Deferral record: `autogenesis/experiences/2026-09-12-explicit-discuss-integration-agent-spec-unavailable.md`
- Implementation: `autogenesis/experiences/2026-09-12-explicit-discuss-integration-implemented.md`

## Related

The plan records the intended package, documentation, and deterministic
contract changes.
