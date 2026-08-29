---
type: experience
title: "Skill nesting requires explicit read_file of target SKILL.md body"
created: 2026-08-18
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: raw
description: "Major discovery: successful skill-from-skill invocation depends on explicit read_file of the inner skill's full SKILL.md path + exact body execution; description alone is insufficient; dynamic secrets prove load+execute."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-18-skill-nesting-read-file-invocation-discovery`.

## What happened

## What the user asked

User wanted to test the theory that "Grok is not able to call skills from within skills". Designed two test skills (skill-test-a invokes skill-test-b) via genesis + skill-creator. skill-test-b produces a dynamic secret from live Unix timestamp. The secret can only be correct if B's logic ran.

## What happened

- Skills created and validated.
- When skill-test-a instructions were followed, the agent performed `read_file` on `/home/workdir/.grok/skills/skill-test-b/SKILL.md`, then executed its body (bash `date +%s` + formula), producing a verifiable secret `NESTED-8025-alpha`.
- Follow-up observation: if `read_file` is *not* used, only the short frontmatter description is available in context. The body (formula, tool calls, exact steps) is invisible. Any "secret" produced is a hallucination and fails verification against the live timestamp formula.

## What was pinned / discovered

1. **Invocation substrate reality**: Skills are *not* automatically nested by the dispatcher. The only reliable way for one skill body to invoke another is:
   - Explicit `read_file` on the absolute (or correctly resolved) path to the target skill's `SKILL.md`.
   - Then follow the loaded body's instructions *exactly*, including any tool calls (bash, etc.).
   - Never rely on prior memory, the short description, or assuming the body is already in context.

2. **Dynamic / non-guessable outputs** are the correct way to prove nested execution (timestamp formula, hash of live state, etc.).

3. **Chained behaviours currently exhibit problems** precisely when this explicit load pattern is omitted or when agents shortcut.

4. This discovery is durable and must become part of Autogenesis lineage and any future skill-chaining instructions. Genesis itself cannot be updated (externally maintained); the pattern must be enforced downstream in Autogenesis and in skills it grows.

## Related

- Continues the skill-growth and activation discipline work ([[raw/experiences/2026-08-16-run-extends-genesis-implemented]], [[raw/experiences/2026-08-16-run-path-modules-implemented]], [[raw/experiences/2026-08-16-run-activation-flow-canonical]]).
- Impacts path modules that perform skill invocation or multi-skill orchestration.
- Requires a new review mechanism for target packages to ensure the explicit-read_file pattern is consistently applied.

## Outcome for Autogenesis

- Must add this experience to lineage.
- Must document clear "how to chain skills successfully" instructions (the read_file + execute body pattern).
- Must introduce a review subskill / path that inspects any target package for correct nesting/invocation hygiene.
- Going forward, any skill-chaining behaviour generated or grown by Autogenesis must bake this pattern in (no silent or description-only invokes).

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
