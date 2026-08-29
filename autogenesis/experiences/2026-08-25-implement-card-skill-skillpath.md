---
type: experience
title: "Implement: card template leads with skill + skill_path"
created: 2026-08-25
work_id: 2026-08-25-card-skill-skillpath
implements: 2026-08-25-card-skill-skillpath
closes: 2026-08-25-card-skill-skillpath
plan_path: autogenesis/plans/2026-08-25-card-skill-skillpath.md
construct_eval: deferred: doc-only schema tweak, no runtime behaviour change
status: raw
origin: internal
sensitivity: internal
relates_to:
  - path: autogenesis/plans/2026-08-25-card-skill-skillpath.md
    kind: implements
  - path: autogenesis/work/2026-08-25-card-skill-skillpath.md
    kind: implements
---

## What the user asked

Small enhancement to the card pattern: the card template should include the skill and skill_path that is activating; these should be the first values in any card. Once done, review all the skills and paths available here and apply the pattern.

## What was done

- Persisted approved plan (hardening) under subject Atlas.
- Updated canonical Enter card + path receipt in `workflow-discipline.md` and B17 `activation-card.md`.
- Updated `run-record-template.md`.
- Propagated the leading `skill:` / `skill_path:` fields to every active skill and path that hard-coded or documented the card:
  - atlas, agent-brain, agent-spec, construct, portfolio, visual, knowledge-crawl, okf
  - agent-brain paths (dream, forget), agent-spec/specify, gamma/medium migrate-project
- Version bumps on affected skills.
- Historical experiences/plans left untouched (no rewrite).

## Changed files

- autogenesis/SKILL.md (v0.3.9)
- autogenesis/references/modules/workflow-discipline.md (v2026-08-25)
- autogenesis/references/modules/patterns/activation-card.md (v0.3)
- autogenesis/references/run-record-template.md
- autogenesis/references/atlas/autogenesis/plans/2026-08-25-card-skill-skillpath.md
- autogenesis/references/atlas/autogenesis/work/2026-08-25-card-skill-skillpath.md
- atlas/SKILL.md (v0.7.1)
- agent-brain/SKILL.md (v0.8.1)
- agent-brain/references/paths/dream.md
- agent-brain/references/paths/forget.md
- agent-spec/SKILL.md (v0.2.1)
- agent-spec/references/paths/specify.md
- construct/SKILL.md (v0.7.1)
- portfolio/SKILL.md
- visual/SKILL.md
- knowledge-crawl/SKILL.md (v0.2.2)
- okf/SKILL.md (v0.2.1)
- gamma/references/paths/migrate-project.md
- medium/references/paths/migrate-project.md

## Path receipt

```text
skill: autogenesis
skill_path: /home/workdir/.grok/skills/autogenesis
subject: autogenesis
path: implement
approved: yes
atlas_root: /home/workdir/.grok/skills/autogenesis/references/atlas
nested_skills_loaded: none (doc-only)
substrate_contract: applied
remember: yes
compile: yes
Enter|Change|Exit: pass
work_id: 2026-08-25-card-skill-skillpath
construct_eval: deferred: doc-only schema tweak
```
