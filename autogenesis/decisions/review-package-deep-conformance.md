---
type: decision
title: "Deep review-package \u2013 multi-facet package conformance"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Migrated knowledge: Deep review-package \u2013 multi-facet package conformance"
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/corpus-experiences.md
    kind: related
---

## Decision

After the 2026-08-18 design + implement run, `path: review-package` is the deep conformance evaluator.

## Facet catalogue (v1)

| Module | Responsibility |
|--------|----------------|
| `validate-skill-import-links` | Substrate-contract wording on every load / hand-off / invoke |
| `validate-progressive-disclosure` | Thin registry, path vs module separation, one-path-at-a-time, on-demand only |
| `validate-okf-conformance` | OKF rules on any embedded `references/wiki/` (via substrate → okf) |
| `validate-gate-map-and-non-goals` | G0–G8 / Enter-Change-Exit honesty + non-goals presence & honesty |

## REPORT shape

See the procedure in `references/paths/review-package.md`. The aggregated REPORT always begins with a genesis design-quality summary, then the four facet results, then overall status and recommended changes.

## Compatibility

The narrow nesting check remains available by loading `references/modules/validate-skill-import-links.md` directly. The deep path is reserved for full evaluation requests.

## Rationale

Migrated from okf-wiki knowledge page `review-package-deep-conformance` during work `autogenesis-okf-wiki-to-atlas-migration-v1`. Substrate authority is now Atlas.

## Consequences

See relates_to; discipline paths use Atlas only.
