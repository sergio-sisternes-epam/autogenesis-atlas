---
type: work
title: SOLID-derived skill design lens
created: 2026-09-12
work_id: 2026-09-12-solid-skill-design-lens
status: designed
description: A pinned new-surface design now defines a skill-native SOLID lens grounded in cohesion, information hiding, change locality, and explicit applicability without forcing modularization or runtime machinery.
relates_to:
  - path: autogenesis/plans/2026-09-12-solid-skill-design-lens.md
    kind: related
  - path: autogenesis/work/2026-09-11-instruction-first-skill-modules.md
    kind: follows
  - path: autogenesis/work/2026-09-11-parent-routed-skill-module-pattern.md
    kind: follows
  - path: autogenesis/experiences/2026-09-11-s8-self-review-diagnostic.md
    kind: derived_from
---

# SOLID-derived skill design lens

## Scope

Define a cross-cutting design lens for Genesis and Autogenesis work, including
root-only skills and parent-routed modules. Translate SOLID into skill-native
questions while making information hiding, cohesion, and change locality the
foundation.

## Guardrails

- SOLID is a design and review lens, not a five-part structural compliance
  checklist.
- The lens must not force modularization, speculative extension points,
  runtime validators, schemas, or empty abstractions.
- Principle-specific checks apply only when the relevant relationship exists,
  especially substitutability, multiple callers, or volatile dependencies.
- Open/Closed means governed extensibility and protection from accidental
  semantic drift, not a prohibition on intentional versioned behavior changes.

## Status

The design choices are pinned and the formal plan is persisted. Implementation
is awaiting explicit approval. The design keeps Genesis read-only, adds one
shared Autogenesis reference, applies it prospectively through existing
authoring/review surfaces, and introduces no runtime module or semantic
validator.

## Outcomes

- [Proposed design and approval boundary](../plans/2026-09-12-solid-skill-design-lens.md)
