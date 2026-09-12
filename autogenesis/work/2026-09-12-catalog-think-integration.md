---
type: work
title: "Replace vendored Autogenesis think modules with catalog think@atlas"
created: "2026-09-12"
work_id: "2026-09-12-catalog-think-integration"
status: designed
description: "Follow-up to explicit Discuss integration: stop forking think-challenge, think-grill, and think-ramble inside Autogenesis. Nest-load catalog think@atlas and keep only Autogenesis Run wrappers."
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/experiences/2026-09-12-catalog-think-overlap-finding.md
    kind: related
  - path: autogenesis/work/2026-09-12-explicit-discuss-integration.md
    kind: follows
  - path: autogenesis/decisions/internal-think-modules.md
    kind: related
---

## Scope

Autogenesis v0.6.0 declares `think@atlas` 0.1.0 but does not activate it.
During a Run, challenge / grill / ramble load vendored copies under
`references/modules/think-*/SKILL.md`. Catalog install is the same three
skill names. Decision `internal-think-modules` currently allows divergence.

This work should design, then implement, replacing those copies with
direct catalog `think` activation (or thin Autogenesis wrappers that
nest-load the catalog bodies). Keep Run-only rules that catalog think does
not own: parent invocation contract, think-challenge as a design validation
gate, and no grill/ramble while catalog Discuss is active.

Out of scope: reopening Discuss adapter work; advancing the Atlas gitlink;
publishing a new Autogenesis release until this design is approved.

## Status

designed — finding recorded; implementation blocked until a persisted
Autogenesis design is approved.

## Outcomes

- Finding: `autogenesis/experiences/2026-09-12-catalog-think-overlap-finding.md`
- Predecessor: `autogenesis/work/2026-09-12-explicit-discuss-integration.md`
- Prior decision: `autogenesis/decisions/internal-think-modules.md`
- Subject issue: `sergio-sisternes-epam/autogenesis#17`

## Related

This is the think-shaped analogue of explicit Discuss integration. Discuss
was a competing user operation. Think is a vendored fork of catalog
primitives used as Run support.
