---
type: work
title: "Harden the catalogue description so an agreed skill-package change activates Autogenesis"
created: "2026-10-12"
work_id: "2026-10-12-catalogue-description-hardening"
status: done
approval_ref: "chat:2026-10-12T07:58Z:sergio"
approved_by: "Sergio Sisternes"
approved_at: "2026-10-12T07:58:00Z"
approval_quote: "Approve the catalogue-description hardening design with the recommended answers, in 0.9.0"
description: "Done: approved hardening of the root catalogue description so a request to change an existing skill package activates Autogenesis. Ship in unreleased 0.9.0."
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/plans/2026-10-12-catalogue-description-hardening.md
    kind: related
  - path: autogenesis/experiences/2026-10-12-catalogue-description-hardening-design.md
    kind: records
  - path: autogenesis/plans/2026-10-12-plan-status-key.md
    kind: related
  - path: autogenesis/plans/2026-10-12-discussion-gate-designed-only.md
    kind: related
---

## Scope

Harden the root catalogue description so a request to change an existing
skill package activates Autogenesis, then routes to design. Ordinary
refactors, non-skill edits, plain discussion, and a mere mention of
SKILL.md must not activate it. No product edit in the design Run.

## Status

approved — Sergio Sisternes, 2026-10-12T07:58Z, approval_ref `chat:2026-10-12T07:58Z:sergio`. Ship in unreleased 0.9.0, no version bump. The trigger task also grades plan status. F1 and F2 stay parked. SKILL.md budget 4500; fix the stale 4000 mention in references/waza-authoring.md. Implemented in sergio-sisternes-epam/autogenesis#29 (stacked on #28; not merged).

done — 2026-10-12. autogenesis#29 (`9c488f7`, review fix `6215b04`): description replaced (887 characters), README summary, trigger task `agreed-change-activates-autogenesis` (also grades plan status proposed|designed) and `skill-mention-near-miss` with fixtures, scenario `catalogue-description-adversarial-v1`, suite_version 20 → 21, CHANGELOG under 0.9.0, waza-authoring budget mention 4500. SKILL.md 4226/4500 tokens. apm.yml and .waza.yaml unchanged. 96 unit tests pass; Waza 0.38.9 model-free V1–V3: references pass, negatives fail. Suite authored, not run against an agent. Plan stays `approved`.

eval_suite_ref: `.apm/evals/autogenesis/` (drafts only; suite files not authored)
behavioural_status: authored-not-run

## Outcomes

- Plan: `autogenesis/plans/2026-10-12-catalogue-description-hardening.md` (status approved)
- 2026-10-12: Approved by Sergio Sisternes (`chat:2026-10-12T07:58Z:sergio`) with the recommended answers.
- Design experience: `autogenesis/experiences/2026-10-12-catalogue-description-hardening-design.md`
- Parked follow-ups, not implement authority: plan status key; discussion-gate designed-only
- No product commit. Parent gitlink left unchanged.

## Related

Frontmatter relationships are authoritative. Implement is the next transition.
