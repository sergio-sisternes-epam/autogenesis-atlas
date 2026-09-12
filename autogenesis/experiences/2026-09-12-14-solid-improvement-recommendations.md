---
type: experience
title: Ranked SOLID follow-ups for Autogenesis
created: 2026-09-12
work_id: 2026-09-12-14-solid-dogfood-autogenesis
status: complete
subject: autogenesis
origin: user
sensitivity: internal
description: The user asked which SOLID-analysis improvements to recommend. Rank high workspace activation and comparative exercises; defer prose dedupe and scenario-count coupling.
relates_to:
  - path: autogenesis/work/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: implements
  - path: autogenesis/experiences/2026-09-12-14-solid-lens-self-analysis.md
    kind: follows
  - path: autogenesis/plans/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: related
---

# Ranked SOLID follow-ups for Autogenesis

## Context

The user asked, based on the SOLID analysis, which improvements to recommend.
This was a ranking discussion, not an implement request and not approval of a
new plan.

## What happened

Recommendations, ranked:

1. High: workspace-source Autogenesis activation so tests exercise this
   branch, not installed v0.4.3.
2. High: three approved comparative design exercises as behavioral evidence.
3. Medium: skill-root-qualified operational loads of the shared lens.
4. Medium: compact good/bad evidence examples without a validator.
5. Medium later: shrink duplicated Atlas/approval/substrate prose.
6. Low: stop exact scenario-count coupling unless the count is governed.

Do not force modules, adapters, or a semantic validator. Treat these as new
design/hardening work, not silent extra scope on the lens pull request.

## Outcome

The ranking became the first-slice versus protostar split in the dogfood plan.
Items 1-2 are the proposed implement slice; 3-6 are parked protostars.
