---
type: decision
title: "Multi-harness substrate contract for skill nesting"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "When any skill body invokes another skill, load the full body via the harness loader and follow it exactly. Applies to atlas activation at Exit."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/corpus-experiences.md
    kind: related
---

## Decision

When any skill body or path module must invoke another skill:

1. Load the full body of the target skill using the harness’s on-demand skill-loader tool.
2. Follow the loaded body instructions exactly.
3. Re-execute any live tool calls the body requires.

This is the only language allowed in skill bodies that chain. Absolute paths are forbidden in the mandatory wording. When Exit needs memory, the target skill is **atlas** (and **okf** for format-only questions).

## Rationale

Unchanged contract; only the typical memory target changed from okf-wiki to atlas.

## Alternatives considered

- Short-description / memory-only activation — rejected (drift and incomplete Exit).

## Consequences

review-package continues to audit packages for this rule.
