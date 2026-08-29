---
type: experience
title: "Reevaluate after Atlas migration — impact on autogenesis discipline"
created: 2026-08-23
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: done
description: "Material knowledge change (memory substrate now Atlas). Subject autogenesis has capability-gap / correctness impact; concrete update proposals emitted. Advisory only."
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: records
  - path: autogenesis/decisions/lineage-and-remember-via-atlas.md
    kind: records
---

## Context

Atlas root for autogenesis was bootstrapped and key authority pages migrated. Reevaluate path run to produce structured proposals so the discipline uses only Atlas.

## What happened

Scope: subject = autogenesis only (peer graph not expanded).

Classification: **correctness + capability-gap** (memory authority still hard-coded to okf-wiki in SKILL.md, workflow-discipline, progressive disclosure text, and Exit rules).

## Outcome

### Impact: autogenesis
- classification: correctness | capability-gap
- rationale: Primary experience source, progressive disclosure step 5, workflow-discipline hard boundaries, and multiple knowledge references still name okf-wiki as the sole ingestion authority. After the substrate decision this is incorrect and will cause agents to activate the wrong skill.
- uncertainty: low
- evidence: decisions/memory-substrate-is-atlas.md, decisions/lineage-and-remember-via-atlas.md, SKILL.md §Experience source, workflow-discipline.md §Hard boundaries

### Update proposals
1. **SKILL.md**
   - Replace “Experience source” section: Primary change memory = subject skill Atlas root (`<subject>/references/atlas/`) via **Atlas** paths (query/remember/work). This skill’s Atlas for meta lineage. Plans remain `artifacts/autogenesis-plans/`. Atlas is the only ingestion authority for process memory of this skill.
   - Progressive disclosure step 5: “If Exit needs memory ops: activate root skill **atlas**, then load the named path module (remember / query / work) — do not invent remember/ingest from memory.”
   - Failure modes: replace “skipping okf-wiki” with “skipping Atlas”.
   - Skill chaining / nesting references that point at old wiki knowledge pages → update or note they live under the new Atlas decisions.
2. **Paths / modules**
   - `references/modules/workflow-discipline.md`: replace every “okf-wiki” / “subject wiki” hard boundary with Atlas root + path modules; update Session vs wiki → Session vs Atlas; remove or retarget [[knowledge/…]] links that no longer exist under the old wiki.
   - Path modules that still say “Exit via okf-wiki” or “write into subject wiki” (reevaluate, implement, design, research, learn-skill, etc.) must be updated to Atlas remember/compile.
3. **Knowledge contracts**
   - Query-first now means `atlas search` against the Atlas root.
   - Required pages: the three new decisions under decisions/.
4. **Open tasks**
   - owner: autogenesis / agent
   - domain: memory-substrate
   - next gate: design (hardening) then implement after approval
   - signature: memory-substrate-atlas-v1

### Decision gate
- This run: **proposal only** (reevaluate rule)
- Implement: requires explicit design/implement approval

## Related

See frontmatter.

## Follow-ups

- Formal design (hardening class) for the concrete text replacements, then implement.
