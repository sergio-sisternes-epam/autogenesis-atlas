---
type: experience
title: "Avoid hard-coded absolute paths in the skill-nesting substrate contract"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Hard-coded full paths (e.g. /home/workdir/.grok/skills/okf-wiki/SKILL.md) are brittle; the contract must use name-based discovery + harness-agnostic load instructions so it survives skill relocation and multi-harness deployment."
relates_to:
  - path: work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: decisions/memory-substrate-is-atlas.md
    kind: related
  - path: decisions/challenge-adversarial-construct.md
    kind: related
  - path: decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-path-resilient-nesting-contract`.

## What happened

## What the operator asked

After the review-package report on autogenesis itself (which flagged abbreviated okf-wiki / genesis / think-challenge invocations), the operator asked:

> Can we find a way to avoid setting full paths, as that would change in the future? Create a memory/experience on this.

## Observation

The current multi-harness substrate contract examples (and the suggested_fix in the review report) still contain absolute paths such as:

```
/home/workdir/.grok/skills/okf-wiki/SKILL.md
/home/workdir/.grok/skills/skill-test-b/SKILL.md
```

These paths are environment-specific and will break when:

- skills are relocated (different skills root, user vs project scope, different harness layout),
- the package is deployed under Cursor (`.agents/skills/…` or `.cursor/skills/…`), Copilot (`.github/skills/…`), Claude Code (`.claude/skills/…`), or a future Grok layout,
- the skill is published via APM / marketplace and the consumer has a different install root.

## Desired resilient pattern

The substrate contract should stay path-free at the instruction level. Prefer:

1. **Name-based discovery**  
   “Locate the skill named `<name>` from the available skills list / skills root that the harness has already surfaced.”

2. **Harness-agnostic load step**  
   “Load the full body of that skill’s entrypoint (SKILL.md) using the harness’s on-demand skill-loader tool.”

3. **Only then** follow the body exactly and re-execute live tools.

Concrete examples of resilient wording:

- “Load the full body of the skill named `okf-wiki` (use the path the harness already shows for that skill, or the standard skills-root lookup).”
- “Apply the multi-harness substrate contract to the skill named `okf-wiki`: discover its SKILL.md via the harness’s skill list / skills root, load the full body, then follow it.”

The per-harness mapping table can still give *illustrative* concrete loaders, but the mandatory contract language itself must not embed absolute paths.

## Related

- Continues the nesting discovery and implement lineage:  
  [[raw/experiences/2026-08-18-skill-nesting-read-file-invocation-discovery]]  
  [[raw/experiences/2026-08-18-implement-skill-nesting-multi-harness]]
- Directly addresses the gaps found by review-package on the autogenesis skill itself (abbreviated okf-wiki / genesis / think-challenge calls).

## Outcome wanted

Update the knowledge page `skill-nesting-invocation-pattern` (and any future suggested_fix text) so the durable contract is path-resilient. Absolute paths become optional examples only, never part of the mandatory wording.

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
