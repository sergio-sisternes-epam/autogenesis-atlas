---
type: work
title: "Epic — GitHub APM + split Atlas repos"
created: 2026-08-29
work_id: 2026-08-29-github-apm-atlas-split
work_level: epic
status: designed
kva: alive
description: "Hub epic. Skills to GitHub packages. Every skill Atlas to <repo>-atlas. Ours wins on existing remotes."
origin: user
sensitivity: internal
stage: design
relates_to:
  - path: autogenesis/plans/2026-08-29-github-apm-atlas-split.md
    kind: related
---

## Scope

**Packages:** atlas, autogenesis, discuss, construct, think (three skills).

**Atlas extracts (all skills with a store):**  
`agent-brain-atlas`, `agent-spec-atlas`, `atlas-atlas`, `autogenesis-atlas`, `construct-atlas`, `discuss-atlas`, `gamma-atlas`, `knowledge-crawl-atlas`, `medium-atlas`, `portfolio-atlas`, `skill-feedback-atlas`, `visual-atlas`, `apm-atlas`, `think-atlas`.

Naming: GitHub repo `sergio-sisternes-epam/<repo>-atlas` unless org changes at login.

**Conflict rule:** local tree overwrites the remote via GitHub file APIs. No clone. After upload we are disconnected.

## Status

designed — waiting approval.

## Outcomes

None until implement. Implement uses the GitHub connection, not `gh`.
---
