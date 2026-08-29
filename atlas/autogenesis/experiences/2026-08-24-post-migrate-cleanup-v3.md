---
type: experience
title: "Post-migrate cleanup iteration 3"
created: 2026-08-24
work_id: post-migrate-cleanup-v1
status: closed
description: "Iteration 3: agent-brain dream path Atlas remember; atlas apm.yml created; autogenesis + agent-brain apm.yml deps/descriptions switched from okf-wiki to atlas."
tags: [cleanup, post-migrate, atlas, apm, iteration-3]
relates_to:
  - path: autogenesis/work/post-migrate-cleanup-v1.md
    kind: implements
  - path: autogenesis/experiences/2026-08-24-post-migrate-cleanup-v2.md
    kind: follows
---

## Context

User requested iteration 3 including creating apm.yml for atlas.

## Changed files

- atlas/apm.yml (new) — name atlas, version 0.7.0, depends on okf
- autogenesis/apm.yml — memory via Atlas; deps atlas + okf; version 0.3.5
- agent-brain/apm.yml — Atlas substrate description; deps atlas + okf + autogenesis; version 0.6.0
- agent-brain/references/paths/dream.md — atlas remember; experiences under autogenesis/

## Outcome

Atlas is an APM-described package. Peer brain/autogenesis package metadata no longer claim okf-wiki as primary memory substrate.
