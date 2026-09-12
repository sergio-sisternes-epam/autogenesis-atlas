---
type: experience
title: PR 7 missed two package-shared template paths
created: 2026-09-12
work_id: 2026-09-12-9-shared-template-path-hardening
status: recorded
origin: derived
sensitivity: internal
description: Late review found that aware-runtime and reflect-challenge used module-relative bare paths for package-shared templates after the module migration.
relates_to:
  - path: autogenesis/work/2026-09-12-9-shared-template-path-hardening.md
    kind: implements
  - path: autogenesis/work/2026-09-11-skill-module-invocation.md
    kind: derived_from
---

# PR 7 missed two package-shared template paths

## Context

The v0.5.0 migration moved Autogenesis procedures under
`references/modules/<module>/SKILL.md` and established explicit resolution
bases. A late "Needs a closer look" review found two surviving bare shared
template references:

- `aware-runtime` named `references/aware-hook-template.md`;
- `reflect-challenge` named `references/behaviour-challenge-template.md`.

From a nested module, those strings imply module-root-relative locations that
do not exist. Both templates actually live under the package skill root.

## What happened

Merged PR #7 corrected both instructions to use
`<skill_root>/references/...` and added focused regression assertions. The
findings arrived after earlier reviews had accepted the broader migration,
showing that inventory and generic link-presence checks were not enough to
prove each reference used the correct resolution base.

## Outcome

The immediate defects are fixed in merged commit `b4f0a0d`. GitHub issue #9
tracks a repository-wide audit and generalized source safeguard so future
modules cannot repeat the same category of path-resolution error.

## Follow-ups

- Distinguish package-shared, module-local, sibling, and external references in
  one deterministic audit.
- Prefer generalized structural coverage over an ever-growing list of
  module-specific string assertions.
- Preserve the instruction-first boundary: no runtime validator or new Python
  script is required.
