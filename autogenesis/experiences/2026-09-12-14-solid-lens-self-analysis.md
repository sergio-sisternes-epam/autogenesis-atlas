---
type: experience
title: SOLID lens self-analysis of Autogenesis
created: 2026-09-12
work_id: 2026-09-12-14-solid-dogfood-autogenesis
status: complete
subject: autogenesis
origin: derived
sensitivity: internal
description: Applying the new SOLID lens to Autogenesis itself found evaluation skew, grep-only coverage, duplicated authority, and depth-sensitive loads. Analysis only; no product change.
relates_to:
  - path: autogenesis/work/2026-09-12-14-solid-dogfood-autogenesis.md
    kind: implements
  - path: autogenesis/experiences/2026-09-12-solid-skill-design-lens-implementation.md
    kind: follows
  - path: autogenesis/plans/2026-09-12-solid-skill-design-lens.md
    kind: related
---

# SOLID lens self-analysis of Autogenesis

## Context

After the lens implementation, the user asked to test the new SOLID lens with
Autogenesis and analyse potential areas of improvement only. The installed
catalog skill was still v0.4.3; the workspace branch carried v0.5.0.

## What happened

The analysis stayed advisory. Six improvement areas were named: workspace
activation, comparative design evidence, skill-root-qualified loads, compact
examples, duplicated root/discipline prose, and exact scenario-count coupling.
No Autogenesis product files were changed for that pass. Genesis was not
edited. The live skill load did not prove the branch.

## Outcome

The diagnostic is now durable memory for follow-on dogfood work. It is not
implement authority. Catalog-versus-workspace skew remains the highest
integrity issue for any claim that Autogenesis dogfooded the lens.
