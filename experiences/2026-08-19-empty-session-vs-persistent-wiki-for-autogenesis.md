---
type: experience
title: "Critical learning for Autogenesis: empty session \u2260 empty subject wiki"
created: 2026-08-19
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "User clarified that persistent wiki accumulation is correct. Empty session = no active run in the current conversation. Autogenesis may need to incorporate this distinction so design/implement/review paths and test plans do not request wiki wipes or false isolation."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-19-empty-session-vs-persistent-wiki-for-autogenesis`.

## What happened

## The distinction
- Subject wiki persistence across sessions = correct and desired.
- “Empty session” = no active training/design/implement run already loaded in the *current conversation*.
- Test plans and path modules must not tell agents to “treat the wiki as empty” or imply that a fresh session should start with a blank subject store.

## Why it matters for Autogenesis
Autogenesis creates and reviews skills that own subject wikis. If its design, implement, review-package or test-plan templates assume or recommend wiki isolation/wipes, they fight the intended memory model.

## Pending decision
Should this distinction be incorporated into Autogenesis as:
- an explicit rule in workflow-discipline / Exit / test-plan guidance, or
- a short knowledge page that design and implement paths must respect, or
- both?

Status: open for planning.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
