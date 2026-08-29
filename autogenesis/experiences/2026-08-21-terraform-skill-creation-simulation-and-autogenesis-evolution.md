---
type: experience
title: "2026 08 21 terraform skill creation simulation and autogenesis evolution"
created: 2026-08-21T00:12:00Z
work_id: autogenesis-okf-wiki-to-atlas-migration-v1
status: open
description: "Migrated experience: 2026 08 21 terraform skill creation simulation and autogenesis evolution"
relates_to:
  - path: autogenesis/work/autogenesis-okf-wiki-to-atlas-migration-v1.md
    kind: implements
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
---

## Context of the simulation (Session 1 → current)

This experience captures a multi-turn simulation that exercised the full progressive-training and skill-growth loop, then surfaced a design gap in autogenesis itself.

### Sequence observed

1. **Fresh skill creation + progressive Train**  
   User asked to create a new skill named `terraform` and run progressive training (agent-brain) on the official HashiCorp AWS Get Started track.  
   Outcome: minimal SKILL.md, full okf-wiki store, Stages 0–3, two shallow knowledge pages. Ingest executed. Report produced.

2. **Skill-feedback on knowledge quality**  
   User: “why the knowledge is so poor? There should be dozens of terms and learnings you could have extracted from raw.”  
   Diagnostic (skill-feedback): missing-capability / incorrect-behaviour — Stage harvest was narrative, not inventory-linked term/procedure harvest. Partial application of agent-brain Train rules.  
   Memory of the diagnostic was written into agent-brain process wiki + pending backlog.

3. **Delta retest under agent-brain 0.2.1**  
   User supplied a retest script demanding ordered inventory, Stage 1 term harvest, Stage 2 procedure harvest, coverage + answerability gate.  
   Outcome: full progressive harvest, four knowledge pages, gate passed, ingest executed, sample queries hit L1. Knowledge quality measurably better.

4. **Discrepancy analysis**  
   User asked to compare wiki knowledge vs model knowledge.  
   Findings: no major factual errors; mild simplifications (variable override order, “JSON or remote”); time-sensitive pins (AMI, provider version); important omissions relative to solid practice (locking, classic backends, for_each/count, moved/import blocks).

5. **Autogenesis design discussion — subskills**  
   User: “autogenesis skill now imagine you need to transform your knowledge into subskills inside terraform…”  
   Response: proposed progressive modules (terraform-state, terraform-cli-workflow, terraform-variables, terraform-modules, terraform-providers) that stay inside the terraform skill, link back to the wiki via explicit “query first” contracts, and respect the “never auto-scaffold root skills without approval” rule. Stopped in discussion mode.

6. **Meta question that produced this experience**  
   User: “I’m interested in your thinking process, as I think this is a missing piece in autogenesis skill Learn. Learn should not only consolidate knowledge, but should reevaluate all its skills based out of the new and updated knowledge. What do you think? How autogenesis skill should evolve?”

## Thinking process (first-person)

When the user asked about the missing piece I did three things in order:

1. **Mapped the current contracts**  
   - agent-brain Learn already does target-scoped impact analysis + advisory handovers + gated definition updates.  
   - autogenesis `learn-skill` is deliberately narrow: peer-link + usage memory, explicit non-goal of peer mutation.  
   So the gap the user felt is real: neither path treats *new knowledge as a force that can challenge the entire skillset*.

2. **Identified the original design rationale**  
   The conservatism exists for two reasons that are still valid:  
   - Prevent silent mutation of skills owned by humans or other agents.  
   - Avoid infinite reevaluation loops (still an open ADR).  
   Pure consolidation is safe; constant reevaluation is powerful and dangerous.

3. **Weighed the proposal**  
   A knowledge substrate that never forces its skills to confront new facts is only half a brain. Consolidation without reevaluation produces sophisticated-looking museums.  
   Therefore the idea is correct and important. The evolution must stay disciplined:

   - Default remains **advisory**.  
   - Reevaluation becomes a **first-class path** (or a mode of learn-skill).  
   - Scope is bounded to skills that declare a dependency (peer-links or knowledge contracts).  
   - Promotion still requires recurrence + human/Git-PR gate.  
   - Loop detection is mandatory.

## Proposed evolution for autogenesis (pinned thinking)

**New (or expanded) path: `reevaluate`**

- **Trigger**: after a successful Train/Learn that produced changed knowledge pages, *or* explicit user request.  
- **Input**: changed knowledge pages + the set of skills that have peer-links or declared knowledge contracts against that domain.  
- **Output (always)**:  
  - Impact report per skill (none / advisory / capability-gap / correctness / safety).  
  - Purely advisory handover experiences written into the *subject* wiki.  
  - Optional open tasks on the training-run plan or the skill’s own backlog.  
- **Never**: mutate another skill’s SKILL.md or path modules in the same run.  
- **Escalation**: if the same gap recurs across sessions, surface a design-plan candidate and stop for approval.

This keeps the existing narrow `learn-skill` (peer-link) intact and gives the stronger behaviour its own named path with clear non-goals.

In parallel, agent-brain Learn could grow a soft “broadcast” signal when the target domain is one that many skills depend on; autogenesis can later pick that signal up.

## Trade-offs explicitly accepted

- Slightly higher ceremony after every substantial Train. Worth it.  
- More open tasks — the backlog becomes the memory of “skills that are now slightly wrong.” That is a feature.  
- No automatic skill rewriting. Silent mutation remains more dangerous than temporary staleness.

## Relation to the terraform simulation

The entire simulation demonstrated the gap in real time:

- First Train produced shallow knowledge.  
- Feedback + 0.2.1 harvest rules produced denser knowledge.  
- Discrepancy analysis showed remaining omissions relative to model knowledge.  
- Subskill design discussion showed how that denser knowledge *should* force a reevaluation of the terraform skill’s surface (state, variables, modules, CLI workflow).  
- Yet nothing in the current autogenesis paths would automatically have asked “does the new knowledge invalidate or expand any existing module contracts?”

That is the missing feedback loop this experience records.

## Status and suggested next action

- Status: open (process experience for autogenesis).  
- Suggested: if the user wants to turn the evolution proposal into a formal design, re-issue an activation card with `mode: run`, `path: design`, subject: autogenesis.  
- Until then this experience stands as durable memory of the simulation and the thinking.

## Changed files (this write)

- raw/experiences/2026-08-21-terraform-skill-creation-simulation-and-autogenesis-evolution.md (this file)

## Outcome

Migrated into Atlas process memory.
