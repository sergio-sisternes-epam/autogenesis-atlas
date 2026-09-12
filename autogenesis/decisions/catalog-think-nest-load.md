---
type: decision
title: "Catalog think nest-load"
created: "2026-09-12"
status: accepted
work_id: "2026-09-12-catalog-think-integration"
description: "Autogenesis think-* support modules nest-load catalog think@atlas. They no longer vendor forked procedure."
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-09-12-catalog-think-integration.md
    kind: implements
  - path: autogenesis/decisions/internal-think-modules.md
    kind: supersedes
  - path: autogenesis/plans/2026-09-12-catalog-think-integration.md
    kind: related
  - path: autogenesis/experiences/2026-09-12-catalog-think-overlap-finding.md
    kind: derived_from
---

## Decision

Autogenesis keeps parent-routed `think-challenge`, `think-grill`, and
`think-ramble` support modules. Each nest-loads the matching catalog skill
from pinned `think@atlas` through the harness skill loader as an external
skill. Autogenesis no longer owns a forked think Process.

Run-only overlays remain in the wrappers: parent invocation, think-challenge
as a design validation gate including named-theory adversarial smokes,
subject-Atlas write-home, and no grill/ramble while catalog Discuss is active.
Nested catalog loads must not re-enter the Autogenesis module.

## Rationale

Decision `internal-think-modules` licensed copies to diverge. They did, while
`think@atlas` stayed a declared unused dependency. Think is Run support, not a
competing user operation, so the modules stay; the primitive bodies do not.

## Alternatives considered

- Keep the vendored fork. Rejected: silent drift.
- Delete the three modules and nest-load from design/workflow-discipline.
  Rejected: overlays need a parent-routed support surface. User chose wrappers.

## Consequences

Root Run routing still targets the wrappers. Catalog `think-*` remain
standalone skills for non-Autogenesis use. Future think procedure changes land
in the catalog package, then the pin, not as Autogenesis forks.
