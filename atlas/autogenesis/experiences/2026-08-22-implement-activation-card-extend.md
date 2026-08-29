---
type: experience
title: "Implement: activation-card-extend (hardened + approved)"
created: 2026-08-22
work_id: autogenesis-activation-card-extend
status: raw
description: "Implement path for work_id autogenesis-activation-card-extend after user hardening + pin + proceed instruction"
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/work/autogenesis-activation-card-extend.md
    kind: implements
  - path: autogenesis/decisions/challenge-adversarial-construct.md
    kind: related
---

## Context

Migrated from okf-wiki raw experience `2026-08-22-implement-activation-card-extend`.

## What happened

## What the user asked (linked chain)
- Original curiosity about card system and extension as optional/debug for any skill/agent.
- Clarifications: apply to new issues/skills; include review-package check.
- “proceed to design” → formal design + plan.
- think-challenge on the plan → four counters.
- Recommendations to harden the four counters.
- Final: “harden the plan with your recommendations. pin the plan and proceed with implementation, capturing discussion, plan, hardening and implementation as linked memories”

## What was done
- Hardened the plan (status → approved) with all four counter mitigations, extra adversarial smokes, residual-risk naming, force-required path, “necessary but not sufficient” rule, three-value limit.
- Implemented:
  - `references/modules/validate-gate-map-and-non-goals.md` — card_check logic.
  - `references/paths/initialise.md` — always emit declaration (default off; force-required supported).
  - `references/modules/workflow-discipline.md` — optional activation-card section + version bump.
  - `SKILL.md` — version 0.3.1 + `activation_card: on` for autogenesis itself.
  - `references/scenarios/activation-card-extend-adversarial-v1.yaml` — full hardened suite.
- Linked memories: design experience, work node, this implement experience, plan file, think-challenge discussion (via this body).

## Changed files
- artifacts/autogenesis-plans/2026-08-22-autogenesis-activation-card-extend.md (hardened + approved)
- references/modules/validate-gate-map-and-non-goals.md (updated)
- references/paths/initialise.md (updated)
- references/modules/workflow-discipline.md (updated)
- SKILL.md (version + activation_card)
- references/scenarios/activation-card-extend-adversarial-v1.yaml (created)
- [[raw/experiences/2026-08-22-design-activation-card-extend]] (prior)
- [[raw/experiences/work-autogenesis-activation-card-extend]] (updated)
- [[raw/experiences/2026-08-22-implement-activation-card-extend]] (this file)

## Residual risks (named, not closed)
- Zombie-flag tax if declaration left forever without cleanup discipline.
- Latent agent skip of optional card under context pressure.
- Static review-package check can be green while runtime omits the card.
These are documented in the plan and in the adversarial suite; A-P1 and future construct runs remain the next hardening steps.

## Ingest deferral
ingest: defer: implement produced product files and experiences; no new durable knowledge pages beyond work/experience nodes. Knowledge-page update (e.g. pending-backlog, implementation-status) deferred to a follow-on remember/ingest if operator requests.

## Path receipt
```text
subject: autogenesis
path: implement
approved: yes
okf_wiki_root: autogenesis/references/wiki
nested_skills_loaded: okf-wiki (wiki-lineage-autogenesis, wiki-remember); okf
substrate_contract: applied
remember: yes
ingest: defer: no new knowledge pages claimed in this Run
Enter|Change|Exit: pass
work_id: autogenesis-activation-card-extend
construct_eval: deferred: scenarios materialised; full green/red construct run left for follow-on
```

## Outcome

Preserved as durable Atlas experience under work `autogenesis-okf-wiki-to-atlas-migration-v1`.
