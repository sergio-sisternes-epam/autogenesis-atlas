---
type: work
title: "Harden root routing for discussion conclusions and forbidden plan paths"
created: "2026-10-11"
work_id: "2026-10-11-root-routing-hardening"
status: done
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
  - path: autogenesis/experiences/2026-10-11-root-routing-hardening-implement.md
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

done — implemented in unreleased 0.9.0 after explicit approval by Sergio Sisternes, 2026-10-11T21:52Z, approval_ref `chat:2026-10-11T21:52Z:sergio`. Quote: "Approve the root-routing hardening design with the recommended answers, in 0.9.0". The plan frontmatter stays approved. That is the G4 record.

eval_suite_ref: `.apm/evals/autogenesis/` at suite_version 15
behavioural_status: authored-not-run

## Outcomes

- Plan: `autogenesis/plans/2026-10-11-root-routing-hardening.md` (status remains approved)
- Design experience: `autogenesis/experiences/2026-10-11-root-routing-hardening-design.md`
- Implement experience: `autogenesis/experiences/2026-10-11-root-routing-hardening-implement.md`
- Product commit `243da8277d82f336d7ecb6b326a91800e13bcd03`. Parent gitlink left unchanged.
- Current successors: `explicit-discuss-integration-adversarial-v2` and `atlas-storage-semantics-adversarial-v5`.
- Dogfood suite_version 15. Evidence tasks were not modified. Suite not run against a model.

## Related

Frontmatter relationships are authoritative. Approval of the plan is the
only legal next transition.
