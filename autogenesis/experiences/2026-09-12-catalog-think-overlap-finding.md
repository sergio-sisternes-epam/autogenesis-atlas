---
type: experience
title: "Catalog think overlaps Autogenesis internal think modules"
created: "2026-09-12"
work_id: "2026-09-12-catalog-think-integration"
status: done
description: "After Autogenesis 0.6.0 shipped, a close-out check found think still vendored internally while think@atlas is a declared unused dependency."
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-09-12-catalog-think-integration.md
    kind: implements
  - path: autogenesis/work/2026-09-12-explicit-discuss-integration.md
    kind: follows
  - path: autogenesis/decisions/internal-think-modules.md
    kind: related
---

## Context

Autogenesis v0.6.0 removed the embedded Discuss adapter and directs durable
discussion to catalog `discuss@atlas`. A close-out question asked whether
`think` is similarly embedded and overlaps the installed `think` skills.

## What happened

Autogenesis declares `think@atlas` 0.1.0 at
`874613a67018c74ee95f857416fb315d2f80b92b` but does not nest-load it.

While a Run is active, `challenge` / `grill` / `ramble` resolve to internal
modules:

- `references/modules/think-challenge/SKILL.md`
- `references/modules/think-grill/SKILL.md`
- `references/modules/think-ramble/SKILL.md`

Harness catalog install exposes the same three names as root skills from
package `think`. Decision `internal-think-modules` says Autogenesis owns
these copies, catalog `think-*` remain for non-Run use, and copies may
diverge.

The copies already diverge. Catalog bodies are 25-34 lines; internals are
40-49 lines. Internals add parent invocation arguments, compact-card
procedure, adversarial-scenario derivation on think-challenge, and a ban
on grill/ramble while catalog Discuss is active.

This is not the same defect as Discuss. Discuss was a competing user
operation. Think is a vendored fork of catalog primitives used as Run
support.

## Outcome

Recorded as follow-up work
`2026-09-12-catalog-think-integration`. Not a closer for 0.6.0. A later
design should nest-load `think@atlas` and keep only Autogenesis wrappers
for Run-owned rules.

## Follow-ups

Design and implement catalog think integration under the work hub. Do not
treat `internal-think-modules` as a permanent fork license without a new
challenged plan.
