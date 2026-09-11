---
type: document
title: Skill module evolution discussion
created: 2026-09-11
work_id: 2026-09-11-skill-module-invocation
status: in-discussion
kva: alive
stage: discussion
artifact: SKILL.md
origin: user
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-09-11-skill-module-invocation.md
    kind: implements
  - path: autogenesis/plans/2026-09-11-skill-module-invocation.md
    kind: related
  - path: autogenesis/decisions/skill-nesting-invocation-pattern.md
    kind: related
  - path: autogenesis/decisions/concept-patterns-module.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
    kind: related
---

# Skill module evolution

## Objective

Discuss the approach, implications, and impact of evolving Autogenesis paths
into modules shaped like Agent Skills. This is exploration, not an approved
design or authority to change product files.

## User proposal

Replace `<skill>/references/paths/<name>.md` with
`<skill>/references/modules/<name>/SKILL.md`. Optionally place supporting
resources under that module's own `references/` directory.

## Current reality and evidence

Autogenesis 0.4.3 distinguishes public traversal paths from internal modules.
Both are progressively loaded documents; neither is a peer catalogue skill.
Root-skill chaining requires actual loading of the target skill body.
The existing patterns module is an internal extension injector, not another
catalogue. These distinctions must not disappear accidentally in a layout move.

The Agent Skills specification, read on 2026-09-11 at
https://agentskills.io/specification, defines a directory with `SKILL.md`,
required name and description, optional supporting directories, and relative
references from the skill root. The name must match the directory.
Its metadata field supports string-valued extension properties.
It recommends shallow reference chains. It does not define a portable nested
module discovery or activation protocol.

The initial Atlas search was `atlas search "module" --root <resolved subject
Atlas> --json`. Relevant pages read: the two decisions linked above.
No existing thesis/current-reality.md or glossary.md was found at the expected
store locations. This conversation origin records the local baseline instead;
no settled module-migration thesis is claimed.

## Interpretation and first pin

A module could be an encapsulated capability with a standard entrypoint,
module-local resources, explicit prerequisites, and a completion contract.
Its format can resemble a standalone skill without granting standalone
activation authority.

The user selected parent-routed modules with skill-shaped packaging. The parent retains
workflow gates, subject, mode, Atlas context, and approval state. Module loading
does not itself grant permission to execute a gated action.

## Impact sketch

- Routing and receipts: distinguish module identity and entrypoint from the
  route or sequence through modules. Do not assume loading every helper is a
  workflow transition.
- Discovery: nested SKILL.md files may be treated differently by installers
  and harnesses. No portable catalogue invisibility has been demonstrated.
- Resource resolution: define the module root explicitly; moved references
  cannot continue implicitly resolving against the package root.
- Existing helpers: workflow-discipline, think modules, patterns, and validation
  modules already occupy the proposed namespace. Uniform packaging need not
  make all of them public entrypoints.
- Migration: update live registries, loader instructions, frontmatter,
  templates, source checks, consumer checks, and scenario expectations.
  Retain historical evidence; any compatibility aliases should point to one
  authoritative implementation rather than duplicate it.
- Cost: local resources improve ownership and extraction prospects, but extra
  indirection or copied governance may increase context and maintenance cost.

## Concrete counterexample

If a harness discovers `implement/SKILL.md` independently and executes it
without an approved plan, the format change has bypassed the existing approval
boundary. This is a reasoning probe, not an executed harness test. A successful
design must preserve prerequisites regardless of the discovery route.

## Current discussion pins

Parent routing is pinned; standalone discovery and activation are not part of
this proposal. The activation-boundary document records the user's selection.
The user also selected one packaging format for current paths and existing
internal helpers, retaining distinct roles. The module-role-scope document
records that second pin.

The emerging model separates skill (catalogue and parent authority), module
(encapsulated instruction unit), role (operation versus support), and workflow
(legal sequencing and gates). These labels explain the direction; an exact
metadata schema or receipt-field rename has not been approved. Passive
references remain resources rather than automatically becoming modules.
Implementation and formal design remain out of scope.

## Illustration

The [module model walkthrough](2026-09-11-module-model-walkthrough.md) shows
candidate root, operation, and support entrypoints plus a paper execution
trace. It preserves the two user pins without treating its proposed metadata
or terminology as approved. A linked protostar records the still-unexecuted
loader compatibility probe.

The walkthrough also records a recommendation for activation terminology:
distinguish skill/module activation actions from their activation cards, retain
legacy vocabulary and serialized contracts, and stage reader compatibility
before changing emitted formats or entrypoint locations. The compatibility
mechanics remain recommendations. The activation-card concept is pinned below.

## Approved activation-card concept

On 2026-09-11 the user approved the activation card as the visible interface
to an invocation request and a visual cue that the request happened.
The card signals a request, not authorisation, execution, or completion.
The walkthrough's programming-analogy section records this pin. It does not
approve a formal migration plan or changes to serialized contracts.

## Store maintenance observation

The sequential policy discussion is now captured in the
[formal design](../plans/2026-09-11-skill-module-invocation.md). User choices
include bounded safe retries and a repository-only first-release cutover,
replacing the earlier agent recommendations for no retry and retained legacy
adapters. The full plan awaits approval; discussion pins do not authorise
implementation.

The new discussion pages compiled successfully. Whole-store Discuss lint
reported existing issues in the August residuals/protostar discussion and
its related experience/work pages (L1, L2, L4, L5). None named this new
discussion. Those historical pages were left unchanged because their repair
is outside this discussion's scope; no whole-store lint pass is claimed.
