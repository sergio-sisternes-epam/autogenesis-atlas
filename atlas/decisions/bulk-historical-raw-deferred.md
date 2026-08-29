---
type: decision
title: "Bulk historical raw experiences deferred from full claim rewrite"
created: 2026-08-23
status: accepted
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
description: "Full-directory migrate placed 179 files into staging. Authoritative knowledge pages promoted. Remaining raw experiences, logs, and legacy SCHEMA left as read-only archive under references/wiki/; not claim-rewritten in this pass."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: follows
  - path: decisions/discipline-enter-change-exit.md
    kind: related
---

## Decision

After full-directory `atlas migrate` of the former okf-wiki store:

1. All **authoritative discipline knowledge** pages that define memory, Exit, gates, and progressive disclosure have been promoted and rewritten as claim-bearing decisions under this Atlas.
2. The bulk of **raw/experiences** (≈139), log artefacts, quality configs, and the old SCHEMA.md remain in the historical archive at `references/wiki/` and are **not** claim-rewritten into this Atlas in this work.
3. Staging is cleared after this decision so compile can go green. Full live bulk migration remains under the deferred work `atlas-bm25-and-live-migration-v1`.

## Rationale

The atlas migrate CLI is designed for selective external content → staging → promote → claims. Dumping an entire legacy store is supported for inventory, but converting every raw experience into a claim-bearing Atlas page in one pass is out of scope for this hardening migration and is explicitly deferred product work.

## Alternatives considered

- Force-promote every raw experience as type experience — rejected (token/time explosion, low value for historical run logs).
- Leave staging non-empty — rejected (compile hard-fails; store unusable).

## Consequences

- Historical lineage can still be read from `references/wiki/raw/experiences/`.
- New process memory writes only to this Atlas.
- A future live-migration work item may inventory and selectively promote high-value raw experiences.
