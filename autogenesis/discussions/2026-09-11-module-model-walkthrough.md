---
type: document
title: Autogenesis module model - illustrative walkthrough
created: 2026-09-11
work_id: 2026-09-11-skill-module-invocation
status: in-discussion
kva: alive
stage: discussion
artifact: SKILL.md
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-09-11-skill-module-invocation.md
    kind: implements
  - path: autogenesis/plans/2026-09-11-skill-module-invocation.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-skill-module-evolution.md
    kind: derived_from
  - path: autogenesis/discussions/2026-09-11-module-activation-boundary.md
    kind: backed_by
  - path: autogenesis/discussions/2026-09-11-module-role-scope.md
    kind: backed_by
---

# Autogenesis, expressed as modules

**Formal handoff:** the
[new-surface design](../plans/2026-09-11-skill-module-invocation.md) now captures
the settled decisions and proposed implementation contract. This walkthrough
retains the conversation's earlier alternatives for provenance. In particular,
legacy adapters are not selected: the user chose a repository-scoped cutover.
The formal plan itself still requires approval.

**Discussion specimen, not an approved design or runnable replacement.**
The user asked to see how Autogenesis could evolve under the two agreed
principles: parent-routed modules and uniform packaging with distinct roles.
Snippets below illustrate changed seams; they do not replace the full existing
procedures. No product files have been migrated.

## 1. Package shape

The current source has 12 operational paths and 9 internal instruction modules.
All 21 become module directories. Passive pattern definitions, templates,
and scenarios remain resources, not modules.

```text
autogenesis/
|-- SKILL.md
|-- apm.yml
|-- apm.lock.yaml
|-- atlas-mesh.json
|-- references/
|   |-- modules/
|   |   |-- design/
|   |   |   |-- SKILL.md
|   |   |   `-- references/
|   |   |       `-- challenge-success-criteria.md
|   |   |-- implement/
|   |   |   `-- SKILL.md
|   |   |-- discuss/
|   |   |   `-- SKILL.md
|   |   |-- workflow-discipline/
|   |   |   `-- SKILL.md
|   |   |-- think-challenge/
|   |   |   `-- SKILL.md
|   |   |-- validate-progressive-disclosure/
|   |   |   `-- SKILL.md
|   |   |-- patterns/
|   |   |   |-- SKILL.md
|   |   |   `-- references/
|   |   |       |-- activation-card.md
|   |   |       |-- template.md
|   |   |       `-- deprecated/
|   |   `-- <remaining modules>/SKILL.md
|   |-- scenarios/
|   `-- <shared references and templates>
`-- scripts/
```

The criteria placement illustrates single-module ownership, not an approved
file move; actual callers must be inventoried before relocating shared files.
Package scripts, dependency pins, Atlas identity, and release mechanics do not
gain a new lifecycle merely because module packaging changes.

## 2. The root remains the router

An illustrative excerpt from the evolved root:

```markdown
# Autogenesis

Grow skills through discussion, design, approved implementation, and memory.
Genesis remains the design foundation.

## Module loading

- Locate this package root from the activated root skill.
- Load `references/modules/workflow-discipline/SKILL.md` before an operation.
- Select one operation from the registry and read its complete SKILL.md.
- Load supporting modules only when the active procedure requires them.
- Supporting loads do not change the active operation.
- Module-local references resolve from that module's directory.
- Resolve sibling modules through this parent's registry, not the global
  skill catalogue. This is a read-and-follow convention, not a new tool.
- External root skills still use the harness's skill-loading mechanism.

## Routing

Discussion defaults to `discuss`. Run mode defaults to `design`.
Workflow discipline controls transitions and approval; a routing match
does not confer permission to execute.
```

Registry entries would link to the actual SKILL.md entrypoint:

| Role | Modules |
|---|---|
| Operation | design, initialise, implement, research, reflect-challenge, learn-skill, reevaluate, aware-runtime, wire, review-package, atlas-migrate, discuss |
| Support | workflow-discipline, think-challenge, think-grill, think-ramble, patterns, validate-skill-import-links, validate-progressive-disclosure, validate-okf-conformance, validate-gate-map-and-non-goals |

This grouping illustrates the complete inventory; the real thin registry
would retain each module's description and explicit entrypoint link.
Roles are proposed vocabulary. Standard packaging does not relax contextual
rules: for example, think-grill and think-ramble remain unavailable in
Autogenesis discussion mode.

## 3. One operation module

Candidate `references/modules/design/SKILL.md` excerpt:

```markdown
---
name: design
description: Design a skill change under an active Autogenesis parent. Produce a challenged, persisted plan and stop for approval.
metadata:
  autogenesis-role: operation
---

# Design

## Entry contract

Require an active Autogenesis parent in run mode and this module selected
as its active operation. Use the parent's subject and resolved Atlas.
Follow the parent's workflow-discipline module. Missing context blocks entry.

## Procedure

1. Assign work_id and classify the change.
2. Load external root skill genesis through the harness skill loader;
   also load the parent's patterns support module.
3. Produce the required design depth for the change class.
4. Load the parent's think-challenge support module; evaluate its counters.
5. Pin decisions and read `references/challenge-success-criteria.md`
   relative to this module's root; apply those criteria.
6. Complete the existing catalogue, behavioural-contract, and evaluation
   requirements, including the adversarial draft where applicable.
7. Persist through Atlas and present the plan. Stop for explicit approval.

## Output

Persisted plan, work_id, pins, acceptance evidence, and an operation receipt.
Successful design is not implementation approval.
```

`name: design` matches the directory name. Custom role information uses the
specification's string-valued metadata map. This key is a proposed convention,
not a standard loader feature or permission system. Registry and metadata
roles would have to agree.

The full migrated body would retain every existing requirement, including
agent-spec's exclusive authorship of behavioural Gherkin. This excerpt does
not author a behavioural contract.

## 4. One support module

Candidate `references/modules/validate-progressive-disclosure/SKILL.md`:

```markdown
---
name: validate-progressive-disclosure
description: Inspect module organisation and loading discipline for an active Autogenesis operation. Return findings without changing the target.
metadata:
  autogenesis-role: support
---

# Validate progressive disclosure

## Entry contract

Require the active parent and caller operation. Do not open another operation
or change its subject, mode, Atlas, approval, or work_id.

## Procedure

1. Check that the root registry is thin and entrypoints exist.
2. Check module names, directories, and registry/metadata role agreement.
3. Check that module-local references resolve from their module roots.
4. Check that loads are on demand and sibling references use parent routing.
5. Check that support loads preserve the active operation and its gates.

## Output

Return the existing facet-style findings to the caller.
Do not mutate the target or grant approval.
```

This is an illustrative validator contract, not an implemented validator.
Other support modules may have different effects: patterns can have
authorised maintenance behaviour. "Support" means subordinate to the active
operation, not universally read-only or universally callable.

## 5. Shared discipline and evidence

`workflow-discipline/SKILL.md` remains the single authority for Enter, Change,
Exit, the gate map, context, and receipt rules. The root owns routing; it does
not introduce a second copy of the workflow engine.

Suggested terminology at the changed interface:

| Existing field or concept | Candidate |
|---|---|
| path: design | operation: design |
| path_module | module_entrypoint |
| path receipt | operation receipt |
| Internal module read | support module load, caller identified |
| Legal path transition | legal operation transition |

Illustrative trace, **not an actual activation receipt**:

```text
parent_skill: autogenesis
mode: run
subject: example-subject
operation: design
module_entrypoint: references/modules/design/SKILL.md
support_modules_loaded:
  - workflow-discipline
  - patterns
  - think-challenge
external_skills_loaded:
  - genesis
  - atlas
result: awaiting-plan-approval
```

The full receipt retains existing storage, lineage, and completion evidence.
No new field replaces approval evidence. Reading an entrypoint is necessary,
not proof that its procedure ran.

## 6. Walkthrough: use Autogenesis to evolve its module discipline

1. The user says "show how this would work". Autogenesis stays in discussion,
   uses its discuss operation, and invokes external root skill Discuss.
   It can produce this specimen but cannot edit product files.
2. A later explicit request for formal design selects the design operation.
   The subject stays autogenesis. The proposed protocol is new-surface.
3. Design loads workflow discipline, patterns, and think-challenge as support;
   it remains the same design operation throughout those loads.
4. Genesis and Atlas remain externally loaded root skills. Their own paths
   do not change just because Autogenesis changed its internal representation.
5. Design persists the complete challenged plan and stops for approval.
6. Only after explicit approval can the parent enter implement. Implement
   independently requires the persisted formal plan and its approval evidence.
7. Implementation follows the approved scope, evaluates changed contracts,
   and records subject-Atlas lineage before claiming completion.

## 7. Paper probes

These are expected outcomes derived from the proposed rules, not executed
harness tests.

| Stimulus | Required outcome |
|---|---|
| "Show the idea" while discussing | Illustration only; no package migration |
| Design loads think-challenge | Active operation stays design |
| User requests implement without a formal approved plan | Block; no product edits |
| A harness discovers implement/SKILL.md directly | Refuse execution without parent context and approval |
| A module references references/example.md | Resolve from that module directory |
| A support entrypoint is missing | Report the missing prerequisite; do not substitute a similarly named catalogue skill |
| Parent loads external Atlas | Use Atlas's current root and path contract, not guessed module paths |

The model is coherent as a paper walkthrough. Actual catalogue behaviour and
deployment of nested SKILL.md files remain unproven. The linked loader probe
is the bounded next experiment, not authority to run a migration.

## 8. Activation vocabulary and compatibility

The user asked whether "activation path" and "activation card" should become
"skill activation" and "skill module activation", with aliases to avoid
breaking changes. The following is the agent's recommendation, not a new pin.

### Separate the action from its declaration

| Term | Meaning |
|---|---|
| Skill activation | Enter a root skill through the harness |
| Skill module activation | Enter a selected module under its active parent |
| Activation card | Structured entry declaration for either activation scope |
| Activation receipt | Evidence of the corresponding completed or blocked work |

"Skill activation card" and "skill module activation card" are qualified uses
of the same record concept. Do not alias an activation card to an activation
action. A declared card is not proof that a body was read or its rules followed.

For an operation module, activation sets or changes the active operation under
the existing gates. A support module runs for its caller without replacing that
operation. A file read alone is a load, not completed activation.

### Aliases need scope

- Legacy "activation path" means skill module activation when it names a
  selected capability such as design. When it means the route through several
  capabilities, call it an activation sequence or workflow instead.
- Keep "activation card", B17, its stable pattern identity, and the existing
  activation_card configuration key. Do not introduce a competing key merely
  to modernise terminology. Preserve off/on/debug and absent-value behaviour.
- Continue accepting old user phrasing and old module identifiers.
- Do not reinterpret an arbitrary filesystem path or a peer skill's path
  protocol as an Autogenesis module.
- The operation/module_entrypoint names in section 5 are candidate semantic
  names, not immediate replacements for emitted legacy fields.

### Additive migration, not simultaneous renaming

1. Document the new concepts and contextual aliases while keeping current
   output fields, identifiers, configuration, and gate behaviour unchanged.
2. Update supported readers and agent instructions to normalise old and new
   representations to one model before gate evaluation. Where readers are
   executable, test the actual parser; prose is not a parser implementation.
3. Continue legacy output by default until consumers explicitly support the
   new representation. Do not emit duplicate alias fields unconditionally:
   strict parsers may reject unknown keys. New output needs a supported
   schema/version or capability selection.
4. Relocate module bodies only with a reviewed compatibility strategy for
   old entrypoint paths. Retained legacy files can be thin forwarding
   adapters with the legacy metadata readers require; the canonical module
   remains the sole procedure body. The adapter must cause the actual new
   body to be loaded, and evidence must report the files actually read.
5. Keep old historical plans and receipts intact. Release a new scenario
   version for changed expectations, retaining historical suites. Legacy
   compatibility checks must still exercise the retained legacy surface.
6. Keep aliases/adapters for the supported compatibility period. Removing
   them is explicitly breaking and requires a separately announced release
   policy; before 1.0, do not assume SemVer alone defines that policy.

If both old and new fields are supplied and they disagree, fail explicitly;
never silently pick the value that grants greater authority. Aliases converge
on one canonical module, not two independently maintained workflows.

### Concrete source evidence

The current activation-card extension scenarios inspect activation_card
declarations and off/on/debug behaviour. Atlas-migrate activation scenarios
read the old references/paths/atlas-migrate.md file and assert literal
path_id, name, and subject_scope fields. The storage-semantics scenario also
reads old internal module locations.

Consequently, a vocabulary alias does not protect file consumers or serialized
contracts. A forwarding adapter alone may also be insufficient for a consumer
that inspects full old content; inventory those readers before claiming
compatibility. The compatibility claim is bounded to documented supported
consumers, not arbitrary unknown clients or byte-identical source files.

The proposal leaves parent routing, approval gates, root-only catalogue
exposure, and external skill invocation unchanged.

### Follow-up: activation path as a physical location

The user asked whether "activation path" should instead name the stored
skill/module location. The agent recommends "activation entrypoint" for the
SKILL.md file and "skill root" or "module root" for its containing directory.
This avoids giving a legacy capability-selection term a second meaning during
the same compatibility window.

For example, the module identity is design; its package-relative activation
entrypoint is references/modules/design/SKILL.md; its package-relative module
root is references/modules/design/. References inside the module resolve
against that module root.

If "activation path" is adopted for location despite that ambiguity, define it
as an explicitly new, scoped location concept (preferably the entrypoint file),
not a reinterpretation of legacy path: design. It cannot simultaneously be an
unqualified alias for module activation and an unambiguous physical address.
Reading an entrypoint is still distinct from activation and does not confer
execution authority. The terminology choice is not yet a user-approved pin.

## 9. Programming analogy: invocation and arguments

The user proposed reasoning about activation as a function and the activation
card as its input parameters, asking whether the terms fit programming.
The subsequent approval pins the activation-card concept below. It does not
authorise product implementation or approve every candidate field name.

### Approved concept: activation card

On 2026-09-11 the user approved:

> Activation card becomes a concept, which is the visible interface, and also
> a visual cue to signal an invocation request happened.

The activation card is the visible interface to an invocation request and
signals that the request was issued. The request carries the target,
arguments, and context; the card presents that request to the human.
The card is not itself execution, permission, or proof of success.
Acceptance, rejection, execution, and completion remain distinct states;
outcome evidence belongs in the receipt.

This is a discussion pin. Existing serialized fields and approval gates remain
unchanged. No specific new visual layout, event schema, or migration is
approved by this concept alone.

The agent's assessment is that activation is closest to a function invocation,
not the function definition. The instruction body and entry contract define
the callable capability. Declared fields are parameters; values supplied on a
particular call are arguments. A containing software module is a namespace or
encapsulation boundary; in this proposed discipline its single SKILL.md also
provides its callable entrypoint.

| Autogenesis concept | Programming analogue |
|---|---|
| Root skill | Public API and routing boundary |
| Module SKILL.md and entry contract | Callable implementation and interface |
| Activation | Invocation |
| Card schema | Invocation request schema |
| Filled activation card | Rendered request: target, arguments, and context |
| Entrypoint path | Implementation location resolved by the loader |
| Required gates | Preconditions and authorisation checks |
| Output | Result |
| Receipt | Execution evidence, distinct from the result |

"Activation" is reasonable lifecycle language but can suggest enabling or
loading rather than executing. "Activation card" is a presentation metaphor,
not a conventional name for an argument object. The cleanest separation is
invocation (action), invocation request (structured input), and activation
card (its human-facing rendering). Existing terminology can remain accepted;
there is no need for a wire-format rename to adopt this conceptual distinction.

The existing card is not purely function arguments: it combines target
identity, semantic input, inherited context, and resolved file locations.
These can be understood separately without immediately splitting the schema.
The root or loader resolves implementation locations; callers select stable
capability identities rather than supplying arbitrary executable paths.

Illustrative pseudocode only:

```text
invoke(
  target = autogenesis.design,
  arguments = { subject, objective },
  context = { mode, work_id, atlas_root }
) -> { result, receipt }
```

Here autogenesis.design is an illustrative parent-qualified identity, not an
actual API or an independent catalogue skill. A support invocation returns to
the caller without replacing its active operation.

The analogy has limits. Modules may perform effects and require a human gate;
they are not pure functions. Writing a request does not prove execution,
loading a file is not invocation, and caller-supplied approval text is not
authorisation. Approval evidence and all inherited restrictions must still be
validated. No enforced runtime or new API exists merely because the vocabulary
resembles one.

## 10. Remaining discussion areas

The user asked whether further areas need discussion. The three pinned
principles remain parent routing, uniform module packaging with distinct
roles, and the card as a visible cue for an invocation request.

The remaining agenda is deliberately bounded:

| Area | Discussion branch |
|---|---|
| Protocol versus executable runtime | [Execution scope](2026-09-11-invocation-execution-scope.md) |
| Caller inputs and inherited context | [Request contract](2026-09-11-invocation-request-contract.md) |
| Nested calls and failure behaviour | [Invocation lifecycle](2026-09-11-invocation-lifecycle.md) |
| Card emission and presentation | [Presentation policy](2026-09-11-activation-card-presentation.md) |
| Supported legacy consumers and deployment | [Existing compatibility probe](2026-09-11-module-loader-probe.md) |

Recommendations on these branches are not user-approved pins. Exact YAML keys,
complete file moves, scenario implementations, and release mechanics can be
resolved during formal design rather than prolonging conceptual discussion.
Independent module publishing, a new runtime, and peer-skill migrations are
not implied by the agreed packaging model.
