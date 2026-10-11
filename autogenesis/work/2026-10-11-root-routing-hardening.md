---
type: work
title: "Harden root routing for discussion conclusions and forbidden plan paths"
created: "2026-10-11"
work_id: "2026-10-11-root-routing-hardening"
status: approved
approval_ref: "chat:2026-10-11T21:52Z:sergio"
approved_by: "Sergio Sisternes"
approved_at: "2026-10-11T21:52:00Z"
approval_quote: "Approve the root-routing hardening design with the recommended answers, in 0.9.0"
description: "Approved hardening design for root-routing wording so a package-changing discussion conclusion starts design, and a user-named plan path is not a storage override. Ship in unreleased 0.9.0."
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/plans/2026-10-11-root-routing-hardening.md
    kind: related
  - path: autogenesis/experiences/2026-10-11-root-routing-hardening-design.md
    kind: records
  - path: autogenesis/plans/2026-09-12-explicit-discuss-integration.md
    kind: follows
  - path: autogenesis/plans/2026-09-05-atlas-storage-semantics.md
    kind: follows
---

## Scope

Harden Autogenesis root routing prose. A request to apply a discussion
conclusion starts formal design and stops at status designed. A user-named
plan path outside the resolved subject Atlas is declined without asking, and
a legacy references/atlas gitlink still routes to migrate.

## Status

approved — Sergio Sisternes, 2026-10-11T21:52Z, approval_ref `chat:2026-10-11T21:52Z:sergio`. Quote: "Approve the root-routing hardening design with the recommended answers, in 0.9.0". Implement may proceed within the approved plan, in unreleased 0.9.0, with dogfood suite_version 15. Not yet implementing.

## Outcomes

- Plan: `autogenesis/plans/2026-10-11-root-routing-hardening.md`
- Design experience: `autogenesis/experiences/2026-10-11-root-routing-hardening-design.md`
- Review corrections are in that plan. Status is approved.
- 2026-10-11: Approved by Sergio Sisternes (`chat:2026-10-11T21:52Z:sergio`). Ship in unreleased 0.9.0; new dogfood tasks bump suite_version from 14 to 15.
- No product files changed. No scenario files materialised.

## Related

Frontmatter relationships are authoritative. Approval of the plan is the
only legal next transition.
