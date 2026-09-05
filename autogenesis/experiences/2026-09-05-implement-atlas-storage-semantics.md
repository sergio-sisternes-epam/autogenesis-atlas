---
type: experience
title: "Implement current Atlas storage semantics in Autogenesis"
created: 2026-09-05
work_id: 2026-09-05-atlas-storage-semantics
status: implemented
plan_path: autogenesis/plans/2026-09-05-atlas-storage-semantics.md
construct_eval: "deferred: Construct is unavailable in the current harness"
origin: internal
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-09-05-atlas-storage-semantics.md
    kind: implements
  - path: autogenesis/plans/2026-09-05-atlas-storage-semantics.md
    kind: implements
---

## Context

Autogenesis v0.3.13 still wrote memory through a package-local
`references/atlas` gitlink while Atlas v0.8.13 required active-repository
mount, resolve, and `.atlas/<host>/<org>/<repo>` write-home semantics. The
drift blocked an Atlas authentication design from starting safely.

## What changed

Relocated the canonical memory gitlink, centralized deterministic subject
Atlas resolution, aligned all consumers, documented single-writer migration
and global APM rollout, added current scenario contracts, and repaired
pre-existing canonical-store schema/page warnings through Atlas-managed schema
and work-lineage operations.

## Changed files

Autogenesis source:

- `.gitignore`
- `.gitmodules`
- `atlas-mesh.json`
- `.atlas/github.com/sergio-sisternes-epam/autogenesis-atlas`
- `SKILL.md`
- `README.md`
- `CHANGELOG.md`
- `apm.yml`
- `references/README.md`
- `references/aware-hook-template.md`
- `references/behaviour-challenge-template.md`
- `references/run-record-template.md`
- `references/modules/workflow-discipline.md`
- `references/modules/patterns/activation-card.md`
- `references/modules/think-ramble.md`
- `references/modules/validate-okf-conformance.md`
- `references/modules/validate-skill-import-links.md`
- `references/paths/atlas-migrate.md`
- `references/paths/aware-runtime.md`
- `references/paths/design.md`
- `references/paths/discuss.md`
- `references/paths/implement.md`
- `references/paths/initialise.md`
- `references/paths/learn-skill.md`
- `references/paths/reevaluate.md`
- `references/paths/reflect-challenge.md`
- `references/paths/research.md`
- `references/paths/review-package.md`
- `references/paths/wire.md`
- `references/scenarios/atlas-migrate-activation-adherence-v2.yaml`
- `references/scenarios/atlas-storage-semantics-adversarial-v1.yaml`

Canonical Autogenesis Atlas:

- `schema.d/autogenesis-memory-types.json`
- `schema.d/autogenesis-memory-types.receipt.json`
- `autogenesis/plans/2026-09-05-atlas-storage-semantics.md`
- `autogenesis/work/2026-09-05-atlas-storage-semantics.md`
- `autogenesis/experiences/2026-09-05-implement-atlas-storage-semantics.md`
- `autogenesis/plans/index.md`
- `autogenesis/work/index.md`
- `autogenesis/experiences/index.md`
- `log.md`
- Historical page-contract repairs for the
  `2026-08-25-specify-only-behavioural-contract`,
  `2026-08-26-discuss-skill-formalization`,
  `2026-08-26-residuals-vs-protostar`, and
  `atlas-migrate-cli-improve-v1` work clusters.

## Validation

- The relocated store resolves from `atlas-mesh.json`.
- All happy-path and adversarial deterministic smokes pass.
- Release surfaces agree on v0.4.0.
- Active workflow text contains no legacy mount/write contract.
- Atlas compile exits zero with no critical findings or warnings.
- Formal Construct evaluation is deferred and not represented as complete.

## Outcome

The source and canonical memory now use one active-repository Atlas authority.
The paused Atlas authentication design may resume only after the Autogenesis
source change and canonical-store commit are published and the separately
approved global APM update installs the released contract.
