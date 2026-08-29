---
type: experience
title: "Implement path: Exit / remember / ingest hardening (approved plan)"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Applied approved plan to enforce full wiki-ingest (or explicit defer) for knowledge-page creation and substrate-contract activation between lineage \u2192 remember \u2192 ingest"
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/discipline-enter-change-exit.md
    kind: related
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/exit-claim-equals-action.md
    kind: related
  - path: decisions/hard-memory-gate.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-implement-exit-remember-ingest-hardening`.

## What happened

## Enter
mode: run
subject: autogenesis
path: implement
path_module: references/paths/implement.md
intent: apply the approved plan at artifacts/autogenesis-plans/2026-08-18-exit-remember-ingest-hardening-handoff.md

## Approved plan
artifacts/autogenesis-plans/2026-08-18-exit-remember-ingest-hardening-handoff.md  
Operator signal: “Proceed”

## What was done (exact scope)

1. Updated root `SKILL.md` Exit activation checklist:
   - Prefer loading `wiki-lineage-autogenesis` via substrate.
   - Added hard knowledge-page rule (full ingest or explicit defer).
2. Rewrote `okf-wiki/references/modules/wiki-lineage-autogenesis.md` so activation of wiki-remember and wiki-ingest uses the full four-step substrate contract; made explicit deferral mandatory.
3. Narrowed `okf-wiki/references/modules/wiki-remember.md`:
   - “Relate + compile” → “Relate (link only)”.
   - Knowledge-page creation is out of scope for remember.
4. Updated Exit sections of `design.md` and `implement.md` to mirror the new checklist.
5. Updated the vocabulary knowledge page with the hardened rules.

## Changed files

- SKILL.md (Exit checklist)
- references/paths/design.md (Exit section)
- references/paths/implement.md (Exit section)
- ../okf-wiki/references/modules/wiki-lineage-autogenesis.md
- ../okf-wiki/references/modules/wiki-remember.md
- references/wiki/knowledge/vocabulary-lineage-remember-ingest.md
- this experience file

## Durable conclusions
The hardened Exit contract and the substrate-protected activation calls are now live.  
Because a knowledge page was materially updated, a full wiki-ingest is required under the new rule. (This experience records the change; the subsequent ingest step will compile it.)

## Outcome

Preserved as durable Atlas experience.
