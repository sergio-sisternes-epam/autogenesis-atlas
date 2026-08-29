---
type: experience
title: "Implemented skill-test-a/b as canonical reference fixture for activation protocol"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Approved design executed: knowledge page, Skill chaining rule, and review-package path now point at skill-test-a \u2192 skill-test-b as the living, harness-agnostic verification of the multi-harness substrate contract."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-implement-reference-fixture-skill-test-ab`.

## What happened

## What was approved and implemented

Design intent: enhance Autogenesis so skill-test-a + skill-test-b become the canonical reference that any harness can use to verify its skill-nesting activation protocol is correct.

Concrete changes applied:

1. Knowledge page `skill-nesting-invocation-pattern.md` — added “Canonical reference fixture” section describing skill-test-a → skill-test-b, the dynamic-secret proof, and name-only reference.
2. Main SKILL.md — Skill chaining rule section now ends with:  
   “The living verification of this contract is the pair **skill-test-a → skill-test-b**. Any harness can re-run that test to confirm its activation protocol is correct.”
3. review-package path — added optional protocol-check recommendation to re-run the reference fixture when the target claims nesting.

No absolute paths introduced. No auto-wiring. Test skills themselves unchanged.

## Durable conclusion

skill-test-a → skill-test-b is now the official living reference fixture for the multi-harness substrate contract inside Autogenesis. Success of that test on any harness is the definitive proof that the activation protocol is correct.

## Related

- [[raw/experiences/2026-08-18-path-resilient-nesting-contract]]
- [[raw/experiences/2026-08-18-implement-skill-nesting-multi-harness]]
- [[raw/experiences/2026-08-18-skill-nesting-read-file-invocation-discovery]]
- [[knowledge/skill-nesting-invocation-pattern]]

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
