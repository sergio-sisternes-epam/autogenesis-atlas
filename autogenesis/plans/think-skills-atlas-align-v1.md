---
type: plan
title: "Hardening: align root think-* skills to Atlas substrate"
created: 2026-08-23
work_id: think-skills-atlas-align-v1
status: done
change_class: hardening
subject: autogenesis
description: "Update the three root catalog skills think-challenge, think-grill and think-ramble so they no longer hard-code wiki-query / wiki-ingest or a hard dependency on okf-wiki. Persistent ops go through multi-harness substrate contract to skill atlas."
relates_to:
  - path: autogenesis/work/think-skills-atlas-align-v1.md
    kind: implements
---

## Intent + scope

Update the three root catalog skills `think-challenge`, `think-grill` and `think-ramble` so they no longer hard-code the legacy verbs `wiki-query` / `wiki-ingest` or a hard dependency on skill `okf-wiki`.

All durable context reads and lasting-note writes must go through the multi-harness substrate contract applied to skill **atlas** (load its `query` or `remember` path module). Conversation-only use (no store present) remains fully supported.

## Non-goals

- Creating any `references/atlas/` or `references/wiki/` under the three think-* skills.
- Touching the internal Autogenesis modules (`autogenesis/references/modules/think-*.md`).
- Changing public triggers, process steps, tone or non-goals of the three skills.
- Adding `activation_card`, paths, scenarios or version bumps.
- Any change to agent-brain, construct or other peers.

## Pins

1. Persistent ops → multi-harness load of **atlas** (`query` for context, `remember` for lasting notes).
2. No remaining tokens `wiki-query`, `wiki-ingest` or hard dependency on skill `okf-wiki` in the three files.
3. Conversation-only path stays intact (no forced store load).
4. Internal Autogenesis think modules left for later clean-up.
5. Only the three `SKILL.md` files are edited.

## Genesis Artifacts

### Intent + scope + non-goals

See above (abbreviated for change-class: hardening).

### Diagrams / interface

n/a (hardening)

### Cost note

Trivial: three small text files; no new runtime cost.

## Acceptance

- Each of the three SKILL.md files satisfies pins 1–3.
- Functional behaviour (triggers, process order, rules) is unchanged.
- No other files are modified.
- Plan and work node exist under the Autogenesis Atlas and compile green.

## Catalogue Review

n/a (pure text / docs hardening; no topology, gate or activation-card change)

## Residual risks

- Temporary inconsistency with the still-okf-wiki internal Autogenesis modules (accepted; scheduled for later autogenesis tidy-up).
- Users who still rely on a pure okf-wiki “session wiki” outside Autogenesis will see the think-* skills become conversation-only until they adopt Atlas (intentional direction of travel).

## Stop for approval

Explicit user approval of work_id `think-skills-atlas-align-v1` received 2026-08-23. Implement may proceed.
