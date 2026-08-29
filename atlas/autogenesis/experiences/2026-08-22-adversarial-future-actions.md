---
type: experience
title: "Future actions after A-P-ADV session close"
created: 2026-08-22
work_id: autogenesis-challenge-adversarial-construct
status: raw
description: "Named hardening actions left open: Exit latest-vs-all, checker script, receipt field, suite-size review."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/work/autogenesis-challenge-adversarial-construct.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/decisions/challenge-adversarial-construct.md
    kind: related
  - path: autogenesis/decisions/discipline-enter-change-exit.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-22-adversarial-future-actions`.

## What happened

Build a memory of possible actions for the future, after we agreed this session can close.

# What we left open

These are **not** implemented. They need a later **hardening** design + approval. They are not a new-surface unless a checker CLI becomes a new contract.

1. **Exit latest vs all** (`autogenesis-adversarial-exit-latest`)  
   Require the latest `*-adversarial-vN` at implement Exit. Keep prior files as regression. Dropping an old version still needs a new design (P6).

2. **Shared checker** (`autogenesis-adversarial-checker`)  
   One `check_adversarial_gate.py` instead of copy-pasted `python3 -c` in YAML. Cheap JSON only: `{"ok":true}`.

3. **Receipt field** (`autogenesis-adversarial-receipt`)  
   Path receipt lists `adversarial_scenarios` actually run.

4. **Suite-size review** (`autogenesis-adversarial-suite-review`)  
   P12: next behaviour-change design reviews how many smokes exist. Every-counter + add-yes/drop-no will bloat.

Out of scope unless separately designed: construct invoking autogenesis to prove Run discipline (forbidden by R1).

# Related

- [[knowledge/adversarial-construct-learnings]]
- [[knowledge/challenge-adversarial-construct]]
- [[knowledge/pending-backlog-active]]
- [[raw/experiences/2026-08-22-adversarial-gate-learnings]]

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
