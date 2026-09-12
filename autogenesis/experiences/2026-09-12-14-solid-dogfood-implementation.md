---
type: experience
title: Implementing Autogenesis SOLID dogfood
created: 2026-09-12
work_id: 2026-09-12-14-solid-dogfood-autogenesis
implements: 2026-09-12-14-solid-dogfood-autogenesis
closes: 2026-09-12-14-solid-dogfood-autogenesis
plan_path: autogenesis/plans/2026-09-12-14-solid-dogfood-autogenesis.md
status: complete
subject: autogenesis
origin: derived
sensitivity: internal
external_ref: sergio-sisternes-epam/autogenesis#14
description: Approved first slice implemented from workspace Autogenesis v0.6.0: workspace-source fail-closed checks, three comparative SOLID exercises, current-suite adversarial smokes, and docs. Catalog v0.4.3 was not evidence.
relates_to:
  - path: autogenesis/work/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: implements
  - path: autogenesis/plans/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: records
  - path: autogenesis/experiences/2026-09-12-14-solid-dogfood-design.md
    kind: follows
  - path: autogenesis/experiences/2026-09-12-14-solid-lens-lineage.md
    kind: related
---

# Implementing Autogenesis SOLID dogfood

## Context

The operator explicitly approved the persisted plan
`autogenesis/plans/2026-09-12-14-solid-dogfood-autogenesis.md` and asked for
the first implement slice on a new parent branch from current GitHub main
after pull request 11 merged. Workspace Autogenesis v0.6.0 was the loaded
skill root. Catalog Autogenesis v0.4.3 was present on this machine and was
not treated as evidence.

## What happened

Loaded skill_root:

`/Users/sergio_sisternes/work/copilot-worktrees/autogenesis/sergio-sisternes-epam-reimagined-bassoon`

Atlas write-home was dedicated store branch
`2026-09-12-14-solid-dogfood-autogenesis` at tip `ad34a8a` (design plus merged
Atlas main license), not catalog main alone.

Product changes stayed inside the approved slice: workspace-source fail-closed
assertions, three comparative exercises with named consequences keep-root /
split / no-adapter, the approved adversarial YAML, suite-index inventory bump
29→30, and CONTRIBUTING / AGENTS / README / CHANGELOG alignment. No Genesis,
B17, or S8 admission edits. No new public skill, private module, Python
script, runtime schema, or semantic validator.

## Actual evidence

Python 3.12 interpreter:
`/Users/sergio_sisternes/.local/share/uv/python/cpython-3.12-macos-aarch64-none/bin/python3.12`

| Check | Result |
|---|---|
| Focused and full `scripts/test_*.py` | 54 tests passed |
| `solid-dogfood-autogenesis-adversarial-v1` smokes | 5/5 passed; workspace-source recorded skill_root |
| `scripts/release_readiness.py` | pass; package_version 0.6.0 |
| `scripts/dependency_contract.py` | pass; 4 direct dependencies and 0 reviewed anchor divergences |
| Consumer `validate_consumer.py` | deferred: not required to prove this slice; GitHub CI remains the release gate |

## Changed files

- `references/scenarios/solid-dogfood-autogenesis-adversarial-v1.yaml`
- `references/scenarios/solid-dogfood-comparative-exercises.md`
- `references/scenarios/suite-index.json`
- `scripts/test_source_contract.py`
- `CONTRIBUTING.md`
- `AGENTS.md`
- `README.md`
- `CHANGELOG.md`
- `scripts/store_contract.py` (governed gitlink pin after this store persist)

## Outcome

The approved first slice is implemented on parent branch
`sergio-sisternes-epam-solid-dogfood-implement`. Parent gitlink may advance to
this dedicated Atlas persist as a store_contract pin. Parked protostars remain
unimplemented.
