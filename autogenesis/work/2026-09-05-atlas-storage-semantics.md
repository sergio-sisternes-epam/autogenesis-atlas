---
type: work
title: "Migrate Autogenesis to current Atlas storage semantics"
created: 2026-09-05
work_id: 2026-09-05-atlas-storage-semantics
status: done
description: "Canonical work hub for replacing legacy skill-local Atlas storage with active-repository mount and resolve semantics."
origin: internal
sensitivity: internal
relates_to:
  - path: autogenesis/plans/2026-09-05-atlas-storage-semantics.md
    kind: related
  - path: autogenesis/experiences/2026-09-05-implement-atlas-storage-semantics.md
    kind: records
  - path: autogenesis/experiences/2026-09-05-atlas-storage-migration-publication-and-review.md
    kind: records
  - path: autogenesis/decisions/policy-lookup-uses-owner-atlas.md
    kind: records
---

## Scope

Migrate Autogenesis source, workflow, scenarios, documentation, release
surfaces, and canonical memory to Atlas v0.8.13 storage semantics.

## Status

Done locally. Upstream publication and the global consumer update remain
separately approval-gated.

## Outcomes

- The Autogenesis memory gitlink lives at the default `.atlas/<atlas_id>` path.
- Workflow discipline resolves subject memory from the active repository and
  fails closed on ambiguity or resolution failure.
- v0.4.0 migration and consumer guidance are documented.
- Current happy-path and adversarial smokes pass.
- The canonical store compiles with no warnings.
- Autogenesis PR #2 is review-clean; its two review findings were corrected in
  `2ff4a72`.
- Policy lookups now resolve the policy owner's Atlas rather than the audited
  subject's store.
- Formal Construct execution remains deferred because Construct is unavailable
  in this harness.

## Related

Frontmatter relationships are authoritative.
