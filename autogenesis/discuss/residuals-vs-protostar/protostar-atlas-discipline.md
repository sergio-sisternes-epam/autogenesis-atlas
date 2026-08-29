---
type: document
title: "Protostars under Atlas discipline and work links"
created: 2026-08-26
status: settled
kva: alive
work_id: 2026-08-26-residuals-vs-protostar
origin: user
sensitivity: internal
stage: discussion
artifact: autogenesis/discuss/residuals-vs-protostar/protostar-atlas-discipline.md
description: "Additional pin candidate: protostars must follow Atlas remember/work rules so type plus relates_to make them findable."
relates_to:
  - path: autogenesis/discuss/residuals-vs-protostar/hub.md
    kind: derived_from
  - path: autogenesis/discuss/residuals-vs-protostar/fix-proposals.md
    kind: follows
  - path: autogenesis/work/2026-08-26-residuals-vs-protostar.md
    kind: implements
---

## User addition

Any protostar should be created in accordance with Atlas discipline and linked to the source of work. Typing/tagging finds the page. Relations set context.

## What Atlas already guarantees

- Types are **recommended, not closed**. `protostar` already compiles if OKF frontmatter is valid.
- Recommended types today: experience, decision, work, lesson, recipe, document. No `protostar` in that list.
- Remember path **work cluster**: if a page has `work_id`, it must `relates_to` the work hub with `kind: implements`, and compile is incomplete if that edge is missing.
- Relation kinds already include derived_from, follows, implements, related, records.

So findability does **not** require a new Atlas query engine. It requires writers to set `type: protostar`, `work_id`, and edges.

## Minimum page contract (proposed, not implemented)

```yaml
type: protostar
work_id: <source work>
kva: alive
growth: true
star_kind: refine | question | counter | probe | tension | action
relates_to:
  - path: <origin conversation or plan page>
    kind: derived_from
  - path: work/<work_id>.md   # or autogenesis/work/<work_id>.md in subject space
    kind: implements
```

Search: `type: protostar` and/or `kva: alive`. Then walk `implements` to the work hub and `derived_from` to the origin.

## Scope review

| Skill | Required for this fix? | Why |
|-------|------------------------|-----|
| **autogenesis** | yes | Exit still invents `residuals/` and does not mandate the contract above. |
| **discuss** | yes | Sprout requires origin `derived_from` but not the work-hub `implements` edge. Placement text still says `residuals/`. |
| **atlas** | not required for correctness | Work-cluster + free types already exist. |
| **atlas** | optional hardening | Add `protostar` to recommended types + a template so remember authors stop inventing folders and skipped fields. |
| **okf** | no | Type remains an open string. |

Recommendation: change Autogenesis + discuss now (when this discussion becomes a design). Open a **separate** atlas work only if we want protostar in the recommended vocabulary. Do not block the Autogenesis fix on that atlas work.
