---
type: decision
title: "Policy lookups resolve the policy owner's Atlas"
created: 2026-09-05
status: pinned
work_id: 2026-09-05-atlas-storage-semantics
description: "An Autogenesis audit reads Autogenesis-owned policy from the Autogenesis store, even when the audited subject has a different Atlas."
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-09-05-atlas-storage-semantics.md
    kind: implements
  - path: autogenesis/experiences/2026-09-05-atlas-storage-migration-publication-and-review.md
    kind: records
  - path: autogenesis/decisions/skill-nesting-invocation-pattern.md
    kind: related
---

## Decision

When an Autogenesis module needs an Autogenesis-owned policy page while
auditing another subject, it resolves the store declared by the activated
Autogenesis package's `atlas-mesh.json`. It mounts that store if missing in the
active git repository, uses only `atlas resolve <atlas_id>` as the root, and
reads the policy there.

The audited subject's Atlas remains the home for subject memory. It is not the
authority for Autogenesis policy.

## Rationale

Store identity follows content ownership, not the current audit target.
Resolving the target subject's Atlas for
`autogenesis/decisions/skill-nesting-invocation-pattern.md` makes the audit
depend on a page that normally does not exist in the target store. Resolving
the policy owner's declared store keeps the audit deterministic without
copying policy into every subject.

The rule was pinned while addressing review feedback on Autogenesis PR #2:
https://github.com/sergio-sisternes-epam/autogenesis/pull/2#discussion_r3940683426

The source correction is commit `2ff4a72` in the Autogenesis migration branch.

## Alternatives considered

- Read the target subject's Atlas: rejected because target stores do not own
  Autogenesis policy.
- Hard-code an absolute store path: rejected because mounts are
  repository-local and harness-dependent.
- Copy the policy into each subject Atlas: rejected because it creates drift
  and multiple authorities.

## Consequences

- Audit modules must distinguish the policy owner from the audited subject.
- The active repository may mount more than one Atlas, each selected by
  explicit identity and resolved independently.
- Policy lookup is read-only; target mutation remains forbidden during review.
