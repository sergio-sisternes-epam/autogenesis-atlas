---
type: decision
title: "Skill nesting / invocation pattern – multi-harness substrate contract"
created: 2026-08-18
work_id: post-migrate-cleanup-v1
status: active
description: "Canonical multi-harness substrate contract for skill nesting. Promoted from legacy wiki during post-migrate cleanup."
tags: [substrate, nesting, multi-harness, canonical]
relates_to:
  - path: autogenesis/work/post-migrate-cleanup-v1.md
    kind: implements
---

# Skill nesting / invocation pattern – multi-harness substrate contract

## Substrate contract (portable, mandatory)

When one skill body (or path module) must invoke / load / execute another skill:

1. Locate the target skill **by name** from the harness’s available skills list / skills root (do not hard-code absolute paths).
2. Load the **full body** of that skill’s entrypoint (SKILL.md) using the harness’s on-demand skill-loader tool.  
   Never rely on the short frontmatter description alone.
3. Follow the loaded body instructions **exactly**.
4. Re-execute any live tool calls the body requires. Do not reuse stale results.

This is the only language that may appear in skill bodies that chain. It is harness-agnostic and path-resilient. Absolute paths are forbidden in the mandatory wording; they may appear only as optional examples in a mapping table.

## Per-harness mapping (illustrative only – not part of the mandatory contract)

The table below shows *how* a harness typically satisfies the load step after the skill has been located **by name**. These are examples; the mandatory contract itself never embeds absolute paths.

| Harness                  | Typical on-demand body loader (after name discovery) |
|--------------------------|-------------------------------------------------------|
| **Grok**                 | `read_file` on the path the harness already surfaces for that skill name |
| **Cursor**               | `read_file` (or Cursor skill loader) after locating `.agents/skills/<name>/` or `.cursor/skills/<name>/` |
| **GitHub Copilot**       | `/skill-name` or Read after locating `.github/skills/<name>/` (or `.agents/skills/…`) |
| **Anthropic Claude Code**| `/skill-name` or Read after locating `.claude/skills/<name>/` |

When Autogenesis grows or reviews a skill that chains, it emits the path-resilient substrate contract and may reference this mapping table for illustration. Harness-specific syntax stays out of the common skill body unless the package is intentionally single-target.

## Why this is required

- Every modern harness implements progressive disclosure: only name + description are pre-loaded; the full body is loaded on demand.
- Description-only or memory-only “invocation” produces hallucinations for any non-trivial or dynamic logic.
- Dynamic secrets / live state (timestamp formulas, hashes, etc.) are the verification method that the inner body actually ran.
- Composition without explicit body loading is a documented failure mode across Grok, Cursor, Copilot and Claude Code.

## Impact on Autogenesis

- All future skill-chaining behaviour grown or designed under Autogenesis **must** emit the substrate contract.
- The `review-package` path audits target packages for presence of the contract (and, when targets are declared, for the corresponding mapping entries).
- This knowledge page is the single source of truth for the pattern.

## Canonical reference fixture

The living verification of the substrate contract is the pair **skill-test-a → skill-test-b**.

- skill-test-a is the outer skill; it applies the path-resilient multi-harness contract to locate and load skill-test-b by name, then follows its body exactly.
- skill-test-b produces a dynamic secret derived from a live timestamp. A correct secret can be obtained only if the inner body actually ran.
- Any harness (Grok, Cursor, Copilot, Claude Code, or a future one) can re-run skill-test-a. Success proves its activation protocol satisfies the contract; failure (hallucinated/static secret or inability to load) proves the protocol is incomplete.
- The pair is referenced by name only; no absolute paths are required.

## Anti-patterns (forbidden)

- Silent path→path or skill→skill invokes without loading the target body.
- “I know what that skill does” shortcuts.
- Computing a nested secret / result without the live tool calls prescribed by the inner skill.
- Hard-coding a single harness’s loader syntax into a multi-target skill body.

