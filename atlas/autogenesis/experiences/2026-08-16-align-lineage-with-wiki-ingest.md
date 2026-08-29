---
type: experience
title: "2026-08-16 Align lineage with okf-wiki wiki-ingest"
created: 2026-08-16
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Root cause: lineage treated as markdown exit ticket; must activate okf-wiki remember + ingest-or-defer."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-16-align-lineage-with-wiki-ingest`.

## What happened

## Why lineage was not associated with wiki-ingest

1. **Lineage was treated as a file shape** (“write `run-lineage-*.md` + validate”) rather than an **intent that activates okf-wiki**.
2. **wiki-remember** was the default close (session pin) even when the Run claimed **durable conclusions** (S1–S4 procedures, design rules) — those require **wiki-ingest** (dual-axis) or **explicit defer**.
3. Shared vocabulary was incomplete in *practice*: agents equated “memory gate green” with structural CLI gates, not with ingest completion.
4. okf-wiki triggers listed remember vs ingest separately; autogenesis “lineage” was not always mapped to both.

## Correct association

| Autogenesis moment | okf-wiki op |
|--------------------|-------------|
| Run did X / gates / reflection | **wiki-remember** |
| Implemented procedures, design vocabulary, lasting rules | **wiki-ingest** (or explicit defer in lineage body) |
| Audit trail | `journal` with `remember` and/or `ingest` |

## Vocabulary
See `knowledge/vocabulary-lineage-remember-ingest.md` (autogenesis) and okf-wiki peer copy.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
