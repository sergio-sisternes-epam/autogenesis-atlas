---
type: experience
title: "Human-gated deletion of migrated wiki archives"
created: 2026-08-24
work_id: post-migrate-cleanup-v1
status: closed
description: "Policy wiki-folder-deletion-policy adopted. User requested delete of all successfully migrated subject references/wiki/ folders. Deleted agent-brain, construct, apm, medium, portfolio, autogenesis wiki trees."
tags: [cleanup, wiki, archive, deletion]
relates_to:
  - path: autogenesis/decisions/wiki-folder-deletion-policy.md
    kind: implements
  - path: autogenesis/work/post-migrate-cleanup-v1.md
    kind: implements
---

## Context

Policy: no auto-delete on migrate; human-gated delete with preconditions. User adopted policy and requested bulk delete of successfully migrated archives.

## Deleted

| Subject | Approx. files removed |
|---------|----------------------|
| agent-brain | 97 |
| construct | 11 |
| apm | 190 |
| medium | 7 |
| portfolio | 15 |
| autogenesis | 179 |

Path removed in each case: `references/wiki/`

## Not deleted

- gamma (no skill wiki)
- think-* (no skill wiki / not full migrate subjects)
- okf-wiki, knowledge-crawl, terraform (excluded from migration plan)

## Preconditions checked

- Each subject had `references/atlas/SCHEMA.json`
- Prior atlas-migrate completed with compile green in this campaign

## Outcome

Legacy wiki archives removed. Process memory remains on skill Atlases only.
