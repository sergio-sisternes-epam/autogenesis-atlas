---
type: protostar
title: Generalize shared-resource path validation
created: 2026-09-12
work_id: 2026-09-12-9-shared-template-path-hardening
status: open
kva: forming
growth: true
star_kind: action
origin: derived
sensitivity: internal
description: Replace two known-case assertions with a repository-wide safeguard for module-local and skill-root resource resolution.
external_ref: "https://github.com/sergio-sisternes-epam/autogenesis/issues/9"
relates_to:
  - path: autogenesis/experiences/2026-09-12-pr7-missed-shared-template-paths.md
    kind: derived_from
  - path: autogenesis/work/2026-09-12-9-shared-template-path-hardening.md
    kind: implements
---

# Generalize shared-resource path validation

## Pending

Audit every live module resource reference and replace the two-case regression
assertion with deterministic coverage that rejects nonexistent or ambiguous
bare package-shared paths.

## Origin

PR #7's final review identified two module entrypoints that retained
root-relative-looking `references/...` strings after moving under
`references/modules/<module>/`. The exact paths were fixed before merge, but
the review exposed a reusable gap in migration and source-validation
discipline.

## Boundaries

- Keep `<skill_root>/...` explicit for package-shared assets.
- Keep genuine module-local references relative to the module root.
- Keep sibling procedure resolution in the parent registry.
- Do not add a runtime validator, a semantic checker, or a new Python script.
- Treat the merged fixes as the baseline; this work provides generalized
  prevention rather than reopening completed defects.

## Tracking

GitHub issue: https://github.com/sergio-sisternes-epam/autogenesis/issues/9
