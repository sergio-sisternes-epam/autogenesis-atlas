---
type: experience
title: "Implement: align root think-* skills to Atlas substrate"
created: 2026-08-23
work_id: think-skills-atlas-align-v1
status: closed
description: "Hardening implement of the three root think-* SKILL.md files. Replaced wiki-query / wiki-ingest / okf-wiki hard dependencies with multi-harness substrate contract to skill atlas (query / remember). Conversation-only path preserved."
tags: [implement, hardening, think-skills, atlas]
relates_to:
  - path: autogenesis/plans/think-skills-atlas-align-v1.md
    kind: implements
  - path: autogenesis/work/think-skills-atlas-align-v1.md
    kind: implements
---

## Context

Approved design packet `think-skills-atlas-align-v1` (hardening). User directed “Update think-* first” then “Approved”.

## What happened

Applied the approved pins:

1. Rewrote the three root SKILL.md files.
2. All durable read/write now routes through multi-harness load of skill **atlas** (`query` / `remember`).
3. Removed every occurrence of `wiki-query`, `wiki-ingest`, hard `okf-wiki` dependency and “session wiki” assumption.
4. Conversation-only use remains fully supported.
5. No other files touched; internal Autogenesis think modules left for later clean-up.

## Changed files

- `think-challenge/SKILL.md` — full rewrite of process + rules + description
- `think-grill/SKILL.md` — full rewrite of process + rules + description
- `think-ramble/SKILL.md` — full rewrite of process + rules + description

## Outcome

- Legacy tokens verified absent.
- Scope exactly matched the approved plan (no creep).
- Construct evaluation: deferred (doc-only hardening; no scenarios owned by the think-* skills).

## Follow-ups

- Later: update internal Autogenesis modules `references/modules/think-*.md` (already noted as residual).
- Next in migration order: agent-brain (full atlas-migrate).
