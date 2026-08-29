---
type: document
title: "Hub: residuals folder vs protostar"
created: 2026-08-26
status: settled
kva: alive
work_id: 2026-08-26-residuals-vs-protostar
origin: user
sensitivity: internal
stage: discussion
artifact: autogenesis/discuss/residuals-vs-protostar/hub.md
description: "Origin node. Autogenesis must not accumulate future work in a residuals folder."
relates_to:
  - path: autogenesis/work/2026-08-26-residuals-vs-protostar.md
    kind: implements
---

## Objective

Review why `residuals/` keeps happening in Autogenesis runs, and settle a replacement: pending future work is a **protostar**, not a residual pile.

## Current reality (this conversation)

On gamma and medium atlas-first work, the agent parked specify / construct / first-live-bootstrap under `autogenesis/residuals/` even after the user had just asked for the protostar term. That is the bug in behaviour.

## Two different words

| Phrase | What it should mean | What it became |
|--------|---------------------|----------------|
| Plan `## Residual risks` | leftover accepted *risks* after challenge | mostly fine, but the word leaks |
| Folder `autogenesis/residuals/` | nowhere | a second backlog next to work/ and plans/ |
| Discuss **protostar** | forming idea worth chasing later | the intended object |

## Growing vs alive

This hub is `kva: alive`. No implement. Children may be protostars.
