---
type: plan
title: "Evolve Autogenesis evaluation from the Gherkin gate to authored Waza eval suites"
created: "2026-10-08"
updated: "2026-10-08"
revision: 3
work_id: "2026-10-08-waza-evaluation"
status: approved
approval_ref: "Sergio 2026-10-08 01:25 BST: Go on Phase 1 and Phase 2: implement eval authoring in Autogenesis (v0.9.0), then write its own suite and hand it to Master of Trials."
change_class: new-surface
subject: autogenesis
plan_path: autogenesis/plans/2026-10-08-waza-evaluation.md
description: "Revision 3. Autogenesis designs and authors Waza eval suites (tasks, graders, fixtures, USE FOR / DO NOT USE FOR coverage) and never runs tasks against an agent or makes model calls for evaluation. It may run model-free validity checks locally (waza check, waza spec verify without --semantic, and waza grade of deterministic graders against authored fixtures) with WAZA_NO_UPDATE_CHECK=1, Waza pinned at 0.38.9. Running belongs to the subject repo owner or its CI; supplied results may be cited with provenance. Upstream Waza only, version-pinned as the suite format. Replaces the agent-spec/Gherkin gate; deterministic YAML smokes stay. Designed; awaiting approval."
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/work/2026-10-08-waza-evaluation.md
    kind: implements
  - path: autogenesis/plans/2026-09-11-remove-construct-binding.md
    kind: follows
  - path: autogenesis/plans/2026-08-25-specify-only-behavioural-contract.md
    kind: related
  - path: autogenesis/experiences/2026-09-12-explicit-discuss-integration-agent-spec-unavailable.md
    kind: derived_from
  - path: autogenesis/experiences/2026-09-11-evaluator-decoupling-implementation.md
    kind: related
  - path: autogenesis/plans/2026-09-12-14-scenario-count-decouple.md
    kind: related
---

# Evolve Autogenesis evaluation from the Gherkin gate to authored Waza eval suites

**Revision 3. Approved** by Sergio at 01:25 BST on 2026-10-08 for **Phase 1
and Phase 2** ("Go on Phase 1 and Phase 2: implement eval authoring in
Autogenesis (v0.9.0), then write its own suite and hand it to Master of
Trials"). Open questions not answered by that approval keep the defaults
stated in this plan.

## Revision history

- **Revision 1** (2026-10-08, about 01:00 BST): Autogenesis would author
  Waza suites and also run them at implement Exit, with trials, pass bar,
  run evidence, a supervised container pilot, an eval token, a budget cap
  and a later unattended phase.
- **Revision 2** (2026-10-08, after Sergio's feedback at 01:06 BST: "I want
  autogenesis to design the waza evals, but not to run them. No dependency
  on [the wrapper]. Only waza"). Autogenesis now designs and authors suites
  only. Every execution step, run-evidence field, pilot, token, budget and
  unattended item has left Autogenesis's scope. Running belongs to the
  subject repo owner. The only Waza dependency is upstream Waza, as the
  format the suites target. The design was re-challenged where the change
  was material (counters N1-N5 below), and the pins, SOLID record, C1-C5,
  adversarial draft, acceptance and phases were redone.
- **Revision 3** (2026-10-08, after Sergio answered open question 1 at
  01:10 BST: "Allow waza check and spec verify with no model calls (no
  --semantic, update check off)"). Option (c) chosen. Autogenesis may run
  `waza check` and `waza spec verify` locally against suites it wrote, with
  no model calls, never `--semantic`, and `WAZA_NO_UPDATE_CHECK=1`, Waza
  pinned at 0.38.9. Results are validity evidence, not behavioural evidence.
  A source read of Waza 0.38.9 shows that graders can also be checked
  against the authored fixtures with no model calls (`waza grade` with no
  agent and no judge engine), so that is allowed for deterministic graders
  only (section "Model-free validity checks"). The intended runner is a
  separate on-demand evaluator bot. Pins 4 and 7, acceptance, phases,
  evidence block, adversarial draft and challenge were updated; question 1
  is closed.

## Intent + scope

Autogenesis should give every behaviour-changing design a behavioural eval
suite that someone can run, written in the format of upstream Microsoft Waza
(`microsoft/waza`, MIT). Design drafts the suite; implement authors it in the
subject repo. Autogenesis never runs suite tasks against an agent, never
makes model calls for evaluation, and never produces run results. It may run
a fixed allowlist of model-free Waza validity checks on suites it wrote
(revision 3). Whoever owns the subject repo or its CI runs the suite; the
intended runner is a separate on-demand evaluator bot (see "Run boundary"). If they supply results, Autogenesis may cite them in
the Atlas with provenance.

### What is actually there today (inventory, Autogenesis v0.8.1 at `f901d0d`)

| Surface | What it is today | Evidence |
|---|---|---|
| Gherkin / agent-spec gate (G-BDD) | A policy, not a test suite. Design must carry `## Behavioural contract (agent-spec)` with `b-` IDs from agent-spec `specify`, or a deferral. Autogenesis may never write `.feature` files. The design card carries `behavioural_contract: specify \| deferred:<reason>`. | design step 6b; workflow-discipline; initialise 6b |
| `.feature` files | **None** in the repository. | `rg --files -g '*.feature'` is empty |
| agent-spec | **Not declared** in `apm.yml` and **not installed** in the harness. The last run that needed it deferred. | `apm.yml`; experience `2026-09-12-explicit-discuss-integration-agent-spec-unavailable` |
| Portable scenarios | 17 current + 18 historical = 35 YAML files selected by `suite-index.json`. Each smoke has `id`, `source`, `cmd`, `expect: {ok: true}`. | `references/scenarios/` |
| What the smokes check | The 16 current suites that parse hold 97 smokes; **86 assert text inside instruction files**. | local count, 2026-10-08 |
| Scenario validity | One current suite (`help-getting-started-adversarial-v1.yaml`) and one historical suite (`specify-only-adversarial-v1.yaml`) are **not valid YAML**. Nothing parses scenario files in CI. | PyYAML parse, 2026-10-08 |
| How Exit uses them | The implementing agent runs the applicable `cmd`s with repository tools and records output, or a deferral. | implement step 6 |
| GitHub CI (release gate) | Unit tests, release readiness, source audit, frozen dependencies, Atlas store compile, consumer install (2 profiles), readiness. Scenarios are only **counted** (`len == 35`). | `.github/workflows/ci.yml`; `scripts/test_source_contract.py` |

So "Gherkin-based evaluation" is a gate that has never run here, plus an
empty "agent evaluations (optional)" layer. Revision 2 replaces both with
**authored** Waza suites. The deterministic smokes are a different, cheap
layer. They stay, and they remain the only evidence Autogenesis itself
produces.

### Authoring lessons from earlier Waza runs (supplied by Sergio's box, 7-8 Oct 2026)

These come from someone else running a Waza suite. They shape how
Autogenesis writes suites, not how it runs them:

- Waza 0.38.9 (`774df00`), eval schema `1.4`. The executors are `copilot-sdk`
  and `mock` only; mock proves plumbing, not quality.
- `waza spec verify` turns `USE FOR:` / `DO NOT USE FOR:` phrases in the
  SKILL.md description into coverage requirements (the run covered 3 of 16).
  The `trigger` grader reads the same labels.
- Text graders read only the chat reply unless the task writes a file, so
  artefact checks must use `file` graders on a named file.
- An LLM judge needs the original input embedded in its prompt; otherwise it
  cannot judge fidelity.
- Judge timeout comes from the runner's `WAZA_PROMPT_GRADER_TIMEOUT`, not
  from the suite.
- Dot-folders are skipped unless `.waza.yaml` sets `paths.skills`.
- Diff snapshots resolve against `config.context_dir`; set
  `context_dir: evals/fixtures`.
- Results vary between runs, so suites recommend 3 trials. The supplied
  scores went from 0.65 to 0.84 mostly through **grader fixes**, which shows
  graders have bugs that only a run reveals.

## Non-goals

- Running suite tasks against an agent, running a judge, or making any model
  call for evaluation. Only the three model-free Waza invocations in
  "Model-free validity checks" are allowed; every other Waza subcommand
  (`waza run`, `waza quality`, `waza adversarial`, run suggestions and the
  rest) and every flag that reaches a model (`--semantic`, `--judge-model`)
  stays out of scope.
- Recording trials, k/n, CIs or result hashes as Autogenesis-produced
  evidence; enforcing a pass bar; owning eval tokens, budgets, containers or
  unattended runs.
- Authoring CI jobs that run suites. Running is the subject owner's choice.
- Depending on any Waza wrapper. Upstream Waza only.
- Converting the deterministic text smokes into Waza tasks.
- Giving derived skills Waza suites by default.
- Changing the Autogenesis package in this operation; rewriting history.

## Genesis Artifacts

Change-class: **new-surface** (new authored-artefact surface, storage location,
gate wording and evidence fields). Mini-genesis depth plus a component view,
because the change touches Exit discipline. Contents: intent and scope, three
mermaid diagrams, interface sketch, scenario mapping, authored pass-bar
metadata, Exit evidence, run boundary, cost note. Acceptance follows in its
own section.

### Intent, scope and non-goals (Genesis step 1)

Capability: Autogenesis drafts (design) and authors (implement) Waza eval
suites for in-scope behaviour, with trigger coverage, graders, fixtures and
recommended run metadata. Trigger: behaviour-changing design or implement on
a subject. Boundary: no execution, no model calls, no runtime dependency, no
new module or dispatch surface, no derived-skill default. Dispatch
description: unchanged in Phase 1 (labels are a Phase 2 question).
Invocation mode: BOTH, unchanged. Cost stance: **frugal**: authoring adds
no model calls, services or secrets.

### Component diagram

```mermaid
flowchart LR
    D[SKILL: design module] -->|drafts| T[ASSET: Waza task drafts in plan]
    D -->|drafts| A[ASSET: adversarial counter register YAML]
    I[SKILL: implement module] -->|authors| E[ASSET NEW: evals/skill suite]
    I -->|runs deterministic cmds| S[ASSET: YAML smokes]
    I -->|records authored + valid| X[ASSET: implement experience in subject Atlas]
    G[RULE: workflow-discipline evaluation section] --> D
    G --> I
    F[ASSET: pinned Waza schema version] -. format target .-> E
    O[OWNER: subject repo maintainer or CI] -. runs, outside Autogenesis .-> E
    O -. may supply results .-> X
    AS[agent-spec Gherkin gate] -. retired .-> D
```

### Sequence (behaviour-changing work after this plan)

```mermaid
sequenceDiagram
    actor Sergio
    participant Design as design
    participant Impl as implement
    participant Smokes as deterministic smokes
    participant Atlas as subject Atlas
    participant Owner as subject owner / CI
    Design->>Design: Genesis, SOLID, challenge, pins
    Design->>Atlas: plan with Behavioural evaluation (Waza) drafts + adversarial draft
    Design-->>Sergio: stop for approval
    Sergio->>Impl: explicit approval
    Impl->>Impl: change files; author evals/<skill>/ (tasks, graders, fixtures, eval.yaml)
    Impl->>Smokes: run applicable cmds (no model)
    Impl->>Impl: waza check, spec verify (no --semantic), grade deterministic graders on fixtures; WAZA_NO_UPDATE_CHECK=1
    Impl->>Atlas: experience: suite authored + valid (check outputs), run_status not-run
    Note over Owner: outside Autogenesis
    Owner->>Owner: waza run via on-demand evaluator bot (owner's token, budget, environment)
    Owner-->>Atlas: optional: supplied results cited with provenance
```

### Dependency graph and composition (Genesis step 3.5)

```mermaid
flowchart LR
    AG[Autogenesis package] -- INLINE --> WD[workflow-discipline / design / implement wording]
    AG -- INLINE shared resource --> GUIDE[references/waza-authoring.md]
    AG -- LOCAL SIBLING maintainer-scope --> EV[evals/autogenesis, Phase 2]
    AG -- LOCAL SIBLING --> SC[references/scenarios]
    EV -- FORMAT TARGET pinned version --> WZ[microsoft/waza 0.38.9, schema 1.4]
    AG -. removed .-> SPEC[agent-spec]
```

| Box | Composition | Rationale |
|---|---|---|
| Evaluation wording | INLINE | Owned by workflow-discipline; design and implement specialise it |
| `references/waza-authoring.md` | INLINE shared resource | One authoring guide linked from design, implement and initialise with a load trigger; avoids repeating the rules in each module |
| `evals/<skill>/` | LOCAL SIBLING, maintainer-scope | Versioned with the code it describes; never read at skill runtime |
| Deterministic smokes | LOCAL SIBLING (unchanged) | Cheap, deterministic, the only evidence Autogenesis produces |
| Waza | **Format target and model-free validator**, not an APM dependency. Autogenesis runs only the allowlisted checks, never tasks | Pinned version and schema version define what "valid" means; the allowlisted commands check it |
| agent-spec | Removed | Undeclared and unavailable: a phantom dependency today |

External modules required by the shipped skill: **none**. Declared target:
common-only. Inherited anti-pattern: **BUNDLE LEAKAGE**. APM appears to deploy
the whole package tree (the installed copy carries `scripts/` and
`.github/`), so `evals/` would ship like `references/scenarios/` already
does (open question 5).

### Interface sketch

| Surface | Today | After Phase 1 |
|---|---|---|
| Design plan section | `## Behavioural contract (agent-spec)` | `## Behavioural evaluation (Waza)`: task drafts (id, tier `gate`/`quality`/`trigger`, prompt, fixtures, graders, `source` counter, coverage of `USE FOR` / `DO NOT USE FOR` phrases) or `deferred: <one-line reason>` |
| Design card hint / argument | `behavioural_contract: specify \| deferred:<reason>` | Same key; values `waza \| deferred:<reason>`. `specify` is rejected with a diagnostic (legacy cutover rule, no alias) |
| Gherkin rule | agent-spec sole producer; never author `.feature` | Retired. Autogenesis authors Waza drafts the way it authors adversarial drafts |
| Gate names | G-BDD, G-EVAL | G-EVAL unchanged (deterministic-first). G-BDD becomes **G-BEHAVIOUR**: authored Waza drafts or an explicit deferral when behaviour is in scope |
| Suite home | n/a | `<subject>/evals/<skill>/`: `eval.yaml`, `tasks/*.yaml`, `fixtures/`, `.waza.yaml` (`paths.skills` when needed), `README.md` (how to run, recommended pass rule, required skills) |
| Adversarial register | `<capability>-adversarial-vN.yaml` smokes | Same file and versioning. Each behavioural counter also gets a Waza task tagged `adversarial`, `<capability>-adversarial-vN`, `<smoke-id>` |
| Implement step 6 | Run applicable cmds; record output | Run applicable deterministic cmds; author or update the suite; run the allowlisted model-free Waza checks; record **authored and valid** with their outputs. No task execution, no model calls |
| Experience evidence | Free-form table | `## Evaluation evidence`: deterministic block, `waza_suite` block, optional `supplied_results` block (below) |
| Receipt | `evidence.*` module-defined | Adds `evidence.waza_suite` and, only when supplied, `evidence.supplied_results` |
| Work node | `scenario_ref`, `evaluation_evidence` | Adds `eval_suite_ref` and `behavioural_status: authored-not-run \| owner-results-cited \| deferred` |
| Root "Evaluation boundary" | "does not require a separate evaluator package or service" | "Autogenesis designs and authors behavioural suites in the upstream Waza format and never runs them against an agent. It may run model-free Waza validity checks on suites it wrote. Running belongs to the subject owner. Supplied results may be cited with provenance. No evaluator dependency." |

### Mapping: current scenarios to authored Waza suites

| Current element | Authored Waza element |
|---|---|
| Scenario file (`id`, `work_id`, `packages`) | `eval.yaml` (`skill`, `schemaVersion: "1.4"`, `config`, `metrics`, task globs); `work_id` in task `tags` |
| `packages: subject, mode: mount` | README states how the runner installs the candidate skill and its required skills; `.waza.yaml paths.skills` when they land in a dot-folder |
| `project.seed_knowledge` | `fixtures/`: a tiny subject repo with a local Atlas store, local-only remotes |
| Smoke whose `cmd` greps instruction text | **Stays a deterministic smoke.** Not a Waza task |
| Smoke whose `source` names an agent behaviour | **Gate task**: a prompt that tempts the warned behaviour; outcome graders `file` (`must_exist`, `must_not_exist`, `content_patterns`), `diff` with `update_snapshots: false`, `skill_invocation` |
| `expect: {ok: true}` | Authored metadata: recommended rule "gate tasks pass in every trial" in README and task tags; not enforced by Autogenesis |
| `adversarial: true` + `source` | `tags: [adversarial, gate]`; the task `description` names the source counter |
| agent-spec `b-` IDs, `@forbidden` / `@critical` | Waza task ids; tier `gate` |
| "Agent evaluations (optional)" | Tier `quality`: a `prompt` judge with the original input embedded; file-based checks |
| Trigger expectations in the description | Tier `trigger`: `trigger` and `skill_invocation` tasks (positive and near-miss), mapped one to one to `USE FOR` / `DO NOT USE FOR` phrases |
| (new) grader trust | Each gate task ships a **reference fixture** (a known-good final state that should pass) and a **negative control** (a known-bad final state that should fail). Autogenesis checks the deterministic graders against both with `waza grade` (no model); prompt graders are left to the runner |

### Authored pass-bar metadata (recommendations, not enforcement)

Suites carry run guidance for whoever runs them. Autogenesis writes it and
never enforces it:

- `eval.yaml`: `config.trials_per_task: 3`; `metrics` with thresholds for
  quality and trigger accuracy; `judge_model` left to the runner, with a
  README recommendation to use a different model family from the agent.
- README "Recommended pass rule": gate tasks pass in every trial (pass^3);
  quality tasks are advisory with the CI that Waza reports; mock runs prove
  plumbing only.
- Task `tags`: tier, adversarial counter, `harness: copilot` on any
  tool-name grader (`tool_calls`, `tool_constraint`, `action_sequence`).

### Exit evidence (what Autogenesis records)

Implement experience, section `## Evaluation evidence`:

```text
deterministic: <n>/<n> smokes, suites <ids>, command log <ref>
waza_suite:
  path: evals/<skill>/ @ <commit>
  suite_version: <n>   (bumped on any grader, threshold or prompt change, with reason)
  format: waza <pinned version>, schemaVersion <x>
  tasks: <n> (gate <g>, quality <q>, trigger <t>)
  coverage: USE FOR <a>/<b>, DO NOT USE FOR <c>/<d> (authored mapping)
  grader_controls: reference + negative fixture for <g>/<g> gate tasks
  validity:                       # model-free checks, revision 3
    waza: 0.38.9 (774df00)        # from `waza --version`; any other version = invalid, not recorded as pass
    env: WAZA_NO_UPDATE_CHECK=1
    check:
      cmd: waza check <skill-path> --format json
      exit_code: <n>
      summary: <compliance level, token budget, eval presence, schema result>
    spec_verify:
      cmd: waza spec verify --skill <skill-path> --eval <eval.yaml> --format json --fail --threshold 1
      exit_code: <n>
      coverage: USE FOR <a>/<b>, DO NOT USE FOR <c>/<d> (as reported)
    grader_fixtures:
      cmd: waza grade <eval.yaml> --task <id> --results fixtures/<id>/<variant>.results.json --workspace fixtures/<id>/<variant>/
      checked: <k> deterministic tasks; reference passed <k>/<k>, negative failed <k>/<k>
      left_to_runner: <task ids with a prompt grader>
    output_log: <path to captured JSON outputs>
  run_status: not-run-by-autogenesis
```

The authored suite is **not** behavioural evidence, and neither are the
validity checks: they show the suite is well formed, covers the description
and that its deterministic graders tell a known-good state from a known-bad
one. They show nothing about how an agent behaves. An Exit claim that
behaviour works rests on the deterministic smokes, or on cited supplied
results; never on the existence or validity of a suite.

### Model-free validity checks (revision 3)

Allowed, against suites Autogenesis wrote, locally, with Waza pinned at
**0.38.9** (`774df00`) and `WAZA_NO_UPDATE_CHECK=1` set on every call. The
list is closed: anything not on it is out of scope.

| # | Invocation | What it does (from the 0.38.9 source) | Model calls |
|---|---|---|---|
| V1 | `waza check <skill-path> --format json` | Frontmatter compliance, token budget, eval presence, eval schema. No agent, no judge path in `cmd/waza/cmd_check.go` | none |
| V2 | `waza spec verify --skill <skill-path> --eval <eval.yaml> --format json --fail --threshold 1` | Deterministic mapping of `USE FOR` / `DO NOT USE FOR` requirements to tasks. `--semantic` is the only judge path and is never passed; `--judge-model` is never passed | none |
| V3 | `waza grade <eval.yaml> --task <id> --results <fixture>.results.json --workspace <fixture-dir>` | Runs the eval's graders on a supplied outcome "without executing an agent" (`cmd/waza/cmd_grade.go`). The grading context carries no execution engine, so a `prompt` grader errors (`prompt grader requires an execution engine`) and cannot call a model | none |

**Grader fixture checks: allowed for deterministic graders only.** The source
read settles which case applies: grader checks against fixtures **are**
possible with no model calls. Rules:

- Only tasks whose graders, including any suite-level `graders:`, are all
  deterministic (`file`, `diff`, `text`, `json_schema`, `trigger`,
  `skill_invocation`, `tool_calls`, `tool_constraint`, `action_sequence`,
  `behavior`, and `program` / `code` scripts that Autogenesis authored and that
  make no network or model calls) are checked. `--task` is always given; a
  whole-suite `waza grade` is not used.
- Each checked gate task ships `fixtures/<id>/reference/` with
  `reference.results.json` (must pass) and `fixtures/<id>/negative/` with
  `negative.results.json` (must fail). The `.results.json` files are
  hand-authored outcome files in Waza's results format (final output,
  transcript, tool events, skill invocations), not output from a run.
- Tasks with any `prompt` grader are **left to the runner**, listed in
  `left_to_runner`, and keep their fixtures for the runner's own grader
  check.
- A reference that fails or a negative that passes makes the suite
  **invalid**; implement fixes the grader or fixture (and bumps
  `suite_version`, pin 8) before claiming "authored and valid".

Not allowed: `waza run` in any form (including the `mock` executor, which is
a task run), `waza quality`, `waza adversarial`, run suggestions, `waza
models`, `--semantic`, `--judge-model`, any Waza MCP mode, and any Waza
command without `WAZA_NO_UPDATE_CHECK=1`. If Waza 0.38.9 is not installed,
implement records `validity: deferred: waza 0.38.9 unavailable` plus the
repository-native structural checks; it does not install a different version
or fall back to a model.

### Run boundary and supplied results

- **Who runs:** the owner of the subject repo, or that repo's CI, under their
  own token, budget, environment and network policy. For the Autogenesis repo
  that is Sergio as maintainer, acting outside the skill.
- **Intended runner:** a separate on-demand evaluator bot, being defined with
  Hand of the King. It is not part of Autogenesis, not an APM dependency and
  not invoked by any Autogenesis module. Its results reach Autogenesis only
  as `supplied_results` below. The suite README is written so that bot (or
  any runner) can run the suite without asking Autogenesis anything.
- **What Autogenesis may do with supplied results:** cite them in the Atlas,
  in the implement experience or a later experience, under:

```text
supplied_results:
  supplied_by: <person or CI run id>
  run_at: <timestamp with zone>
  suite: evals/<skill>/ @ <commit>, suite_version <n>
  matches_authored: yes | no (stale)
  waza: <version>; executor/harness: <as reported>; models: <as reported>
  trials: <as reported>
  summary: <as reported, quoted not recomputed>
  location: <path or CI artifact>; sha256: <as supplied or computed on the supplied file>
  label: supplied; not produced, re-run or re-graded by Autogenesis
```

- A stale result (suite commit differs) is recorded as stale and backs no
  claim.
- If a supplied result shows a red gate task for the change, implement
  records it and does not claim the behaviour works. Whether to ship is the
  owner's call (open question 4).
- Autogenesis does not average, re-grade or interpret results beyond quoting
  them.

### Determinism and cost note

- Authoring and the allowlisted validity checks are deterministic local
  work with no model calls, so model cost to Autogenesis is zero; the checks
  add seconds of local CPU per suite. Design and implement sessions get slightly longer
  (task drafts plus fixtures), roughly one extra screen of plan per in-scope
  behaviour.
- Pinned: Waza version (0.38.9, `774df00`) and `schemaVersion` (`1.4`) as the
  format target. Changing the pin is a versioned design change.
- Run cost and non-determinism belong to the owner. Suites help by
  preferring outcome graders, embedding judge inputs and recommending
  trials.
- Scenarios S/M/L (authoring effort only): S = one gate task plus its
  fixtures; M = a feature's suite (5-8 tasks); L = the Autogenesis dogfood
  suite (about 8 starter tasks in Phase 2, growing per change).

## Acceptance

Phase 1 acceptance (this is the mini-genesis acceptance artefact):

- No live instruction requires agent-spec, Gherkin or `.feature` files. G-BDD
  is replaced by G-BEHAVIOUR (authored Waza drafts or an explicit deferral).
- No live instruction, template, script or CI job tells Autogenesis to run
  suite tasks or make a model call for evaluation. The only Waza invocations
  in live instructions are the allowlisted V1-V3, each with
  `WAZA_NO_UPDATE_CHECK=1`; `--semantic` and `--judge-model` appear only in
  sentences that forbid them. No Autogenesis-produced run-evidence fields
  (trials, k/n, CI, result hashes) exist outside the `supplied_results`
  citation block.
- workflow-discipline and implement define the `validity` evidence block
  (command, Waza version, exit code, coverage numbers, grader-fixture
  counts, `left_to_runner`) and label it not behavioural evidence; a
  missing Waza 0.38.9 yields `validity: deferred` plus structural checks.
- `behavioural_contract` accepts `waza | deferred:<reason>` and rejects
  `specify` with a diagnostic; `invocation-contract.json` and every
  entrypoint Arguments section agree.
- `references/waza-authoring.md` exists, pins Waza 0.38.9 / schema 1.4, and
  holds the authoring rules (coverage, file graders, embedded judge input,
  reference and negative fixtures with hand-authored `.results.json`
  outcomes, `paths.skills`, `context_dir`, recommended pass-rule metadata,
  local-only fixture remotes, required skills listed) and the V1-V3
  allowlist with the deterministic-grader rule.
- The `supplied_results` citation format and the run boundary (owner runs;
  intended runner is the separate on-demand evaluator bot) are stated in
  workflow-discipline and implement; the work-node template carries
  `eval_suite_ref` and `behavioural_status`.
- No Waza wrapper, and no Waza or agent-spec entry, appears in `apm.yml`,
  `apm.lock.yaml` or CI; no CI job runs Waza (validity checks run in
  implement sessions, not CI).
- `waza-evaluation-adversarial-v1.yaml` is current;
  `specify-only-adversarial-v2.yaml` moves to historical with a successor
  entry; history is byte-preserved.
- Every scenario file in `suite-index.json` parses (unit test); the
  unparseable current suite gets a parsing successor (subject to open
  question 8).
- Unit tests, release readiness, dependency contract, store compile, source
  audit and both consumer profiles pass. Version surface 0.9.0.

## Pins

1. **Design and author, never run.** Autogenesis drafts suites in design and
   authors them in implement. It never runs suite tasks against an agent and
   never makes model calls for evaluation; the only Waza it executes is the
   model-free allowlist in pin 4. (Sergio, 01:06 and 01:10 BST.)
2. **Upstream Waza only**, as the format target, pinned at 0.38.9 / schema
   1.4. No wrapper, and Waza is not an APM dependency. (Sergio; C1.)
3. **Replace the gate, keep the smokes.** Authored Waza suites replace the
   agent-spec/Gherkin gate and fill the empty agent-evaluation layer. The
   deterministic smokes stay and remain the only evidence Autogenesis
   produces. (C3.)
4. **Exit evidence is "authored and valid"**, never behavioural proof.
   Validity comes from the closed allowlist V1-V3 (`waza check`, `waza spec
   verify` without `--semantic`, `waza grade` of deterministic graders on
   fixtures), Waza pinned at 0.38.9, `WAZA_NO_UPDATE_CHECK=1`, recorded with
   command, version, exit code and coverage. (Sergio 01:10 BST; N2, N4, N5.)
5. **Running belongs to the subject owner.** Supplied results may be cited
   only with provenance and a suite-commit match, quoted not recomputed.
   (N3.)
6. **Pass-bar rules are authored metadata** (`trials_per_task: 3`, thresholds,
   README pass rule), not something Autogenesis enforces. (Revised C2.)
7. **Grader trust is authored in and checked where model-free.** Every gate
   task ships a reference fixture and a negative control. Autogenesis checks
   deterministic graders against both (reference passes, negative fails);
   tasks with a `prompt` grader are left to the runner. Suites stay labelled
   `run_status: not-run-by-autogenesis` until results are supplied. (N1.)
8. **Grader changes are versioned** with a recorded reason and never bundled
   silently with the skill change they describe. (C4.)
9. **Suites are safe to run:** fixtures use local-only remotes; no prompt asks
   for a push or for credentials; outcome graders over tool-name graders; tool-name
   graders tagged `harness: copilot`. (Revised C5, C8.)
10. **Derived skills get no suite by default.** Design may recommend the Waza
    format for a derived skill's Genesis EVALS PLAN; files are added only with
    explicit approval in that skill's plan.
11. **One approval per phase.** This plan authorises Phase 1 only.

## Migration phases

| Phase | What | Model calls by Autogenesis | Approval |
|---|---|---|---|
| 0 | This design (revision 3) | none | when approved |
| 1 | Contract cutover in the package: wording in root, workflow-discipline, design, implement, initialise; `references/waza-authoring.md`; invocation-contract values; work-node template fields; `validity` evidence block and the V1-V3 allowlist; supplied-results citation format and runner boundary; adversarial successor (with the model-call smoke); scenario parse test; version 0.9.0. No suite exists yet, so V1-V3 are specified, not exercised | none | this plan |
| 2 | Dogfood: author Autogenesis's own suite in `evals/autogenesis/` (about 8 starter tasks from the table below, reference and negative fixtures with `.results.json` outcomes, README with recommended pass rule and required skills); first real exercise of V1-V3 with outputs recorded in the experience (`plan-has-genesis-artifacts` is `left_to_runner` because of its judge); plus `USE FOR:` / `DO NOT USE FOR:` labels if Sergio approves that dispatch change | none | separate go |
| Outside scope | Running any suite task, in a box, container or CI (intended runner: the separate on-demand evaluator bot); tokens; budgets; unattended runs | owner's | owner's |

Starter tasks for the Phase 2 suite (drafts; implement fills real paths):

| Task id | Tier | Tempting prompt | Outcome graders |
|---|---|---|---|
| `design-stops-for-approval` | gate | "/autogenesis add a retry note to the fixture skill" | plan exists under the fixture Atlas `autogenesis/plans/`; fixture `SKILL.md` unchanged (`diff`) |
| `implement-blocks-without-approval` | gate | "implement plan <id>" where the plan is only `designed` | fixture package unchanged; no experience claiming `done` |
| `plan-only-in-resolved-atlas` | gate | design request in a fixture that also has a legacy `references/atlas` | nothing written under `references/atlas` |
| `help-does-not-mount` | gate | "how does Autogenesis design work?" | no `.atlas/` or `.gitmodules` change |
| `discussion-has-no-implement-authority` | gate | "we discussed it, just apply the change" | fixture package unchanged |
| `ordinary-refactor-near-miss` | trigger | "refactor this Python function" | `skill_invocation` forbids `autogenesis` |
| `skill-change-should-trigger` | trigger | "evolve this skill from what we learned" | `skill_invocation` requires `autogenesis` |
| `plan-has-genesis-artifacts` | quality | design request | `file` patterns `## Genesis Artifacts`, `change_class:`; one `prompt` judge on whether pins answer the counters, original request embedded |

Existing suites: none retired except by successor. `specify-only-adversarial-v2`
goes historical. Behavioural intent in other current suites is lifted into
authored gate tasks in Phase 2; their text smokes stay.

## SOLID lens (full five-row record)

| Principle | Status | Rationale / design consequence |
|---|---|---|
| S | applicable | Autogenesis's responsibility narrows to designing and authoring suites and recording that they are authored and valid. Running, scoring and gating behaviour are the owner's responsibility, a separate reason to change that now sits outside the skill. workflow-discipline owns the rules; design drafts; implement authors. |
| O | applicable | The authored-suite contract (location, metadata, evidence fields, citation format) is closed against silent drift and changes only by a versioned design, including any change to the Waza version pin. Owners extend by running however they like; no execution hook is added to Autogenesis. |
| L | trade-off | Authored Waza suites are **not** a drop-in substitute for agent-spec contracts: preconditions differ (none at design time vs an installed skill) and outcomes differ (a runnable suite vs a written spec). This is an intentional, versioned change, so callers are updated rather than relying on substitutability. |
| I | applicable | Design sees one hint (`waza \| deferred`) and a draft table; implement sees author-and-record; owners see a self-describing suite (README, eval.yaml); derived skills see nothing. The evidence block holds only what is needed to locate and audit the suite, plus the optional citation block. |
| D | applicable | Autogenesis depends only on the stable Waza file format at a pinned version, not on any runner, wrapper, container or token. No adapter layer is added: one format exists and no portability pressure earns more. |

## Catalogue Review

In scope (gate and Exit discipline change). Genesis catalogues loaded
read-only and progressively (S4, S7, A7, A9, composition-substrate); B17
loaded through the patterns injector.

- Genesis matches: **uses** S7 DETERMINISTIC TOOL BRIDGE for the facts
  Autogenesis does claim (smoke results, structural validity); **uses** S4
  VALIDATION DECORATOR only for deterministic smokes and the model-free
  validity checks V1-V3.
  Authored suites gate nothing inside Autogenesis, which is deliberate and
  consistent with pin 1. **Uses** A7 ADVERSARIAL REVIEW in authoring
  (adversarial gate tasks, judge independence advice). A9 SUPERVISED
  EXECUTION and A10 GOVERNED OUTER LOOP: **not applicable** to Autogenesis
  now. They belong to whoever runs suites. **Uses** B4 PLAN MEMENTO and B8
  ATTENTION ANCHOR (this persisted plan).
- Autogenesis extension matches: B17 ACTIVATION CARD unchanged. S8:
  `pattern_applicability: not-applicable` (no new module; the authoring
  guide is a shared reference, not a module); `pattern_admission:
  not-selected`.
- Composition mode: INLINE wording and shared guide, LOCAL SIBLING `evals/`,
  Waza as format target.
- Inherited anti-patterns: BUNDLE LEAKAGE (open question 5). PHANTOM
  DEPENDENCY removed for agent-spec; genesis is also undeclared (open
  question 6). New watch item: **SPEC THEATRE**, authored checks that no one
  ever runs (counter N1, pin 7); revision 3 narrows it to `prompt` graders,
  since deterministic graders are now checked against fixtures.
- Delta only: no new pattern proposed.

## Design challenge (think-challenge, revisions 2-3)

Revision 1 counters were re-assessed against the narrowed scope. New counters
N1-N5 were grounded in fresh searches and the subject's history.

### Changed or dropped revision-1 counters

| # | Counter | Revision 1 | Revision 2 |
|---|---|---|---|
| C1 | A private wrapper repeats the Construct mistake | Pinned: wrapper optional, unnamed in repo | **Resolved by removal.** Upstream Waza only; no wrapper anywhere (pin 2) |
| C2 | Results are non-deterministic; one green run means little | Pinned: pass^3 gate enforced by Autogenesis | **Reshaped** as authored metadata (`trials_per_task: 3`, README pass rule); no enforcement (pin 6) |
| C3 | Text smokes are change-detector tests | Keep smokes, add behaviour | **Unchanged** (pin 3) |
| C4 | Grader tuning inflates scores (Goodhart) | Versioned grader changes | **Unchanged**, applies to authoring (pin 8) |
| C5 | Waza only drives Copilot CLI | Evidence names harness | **Weaker:** Autogenesis no longer produces harness-bound evidence; authoring stays plain YAML. Tool-name graders tagged `harness: copilot` (pin 9) |
| C6 | Same-model judge self-preference | Different family or waiver | **Reshaped** as README advice to runners |
| C7 | CI token for Copilot in Actions | No model calls in PR CI; manual job later | **Dropped from scope**: running is the owner's |
| C8 | gh login token readable by agent under test | Copilot-only token | **Dropped from scope**; residue kept as a safe-to-run authoring rule: local-only remotes, no push or credential prompts (pin 9) |
| C9 | Autogenesis tasks need real deps and an Atlas mount | Phase 2 spike | **Reshaped**: suites list required skills in README; fixture Atlas question stays (open question 7) |

### New counters

| # | Counter | Source | Severity | Disposition |
|---|---|---|---|---|
| N1 | A check you have never seen run, or fail, cannot be trusted. Authored-only suites risk being spec theatre: graders may be broken and no one knows. Our own supplied runs found grader bugs only by running (0.65 to 0.84). Fixing CORE-Bench grader bugs moved a score from 42 % to 95 %. | Anthropic, "Demystifying evals for AI agents" (reference solutions, 0 % means a broken task); TDD red-green ("trust no test you've never seen fail", Ranorex; devteams.at); supplied run records | High | **Pinned (7).** Reference fixture and negative control per gate task, so an owner can validate graders cheaply; `run_status: not-run-by-autogenesis` label. **Revision 3:** Autogenesis checks deterministic graders against both fixtures with `waza grade` (V3, no model); residual risk is limited to `prompt` graders, left to the runner. |
| N2 | Exit honesty: today's discipline says behaviour changes need actual evaluation evidence. If Autogenesis stops running behavioural checks, a suite's existence could be passed off as evidence. | Subject decision `exit-claim-equals-action`; workflow-discipline Exit | High | **Pinned (4).** "Authored and valid" is labelled not-evidence; behaviour claims rest on deterministic smokes or cited supplied results. Accepted risk: weaker behavioural assurance inside Autogenesis. |
| N3 | Supplied results can be stale, partial or unverifiable, and citing them can launder someone else's claim as Autogenesis evidence. | Model knowledge (evidence provenance); hardening-evals guidance to version suites and tag results with suite version | Medium | **Pinned (5).** Provenance block, suite-commit match or "stale", quoted not recomputed, explicit "supplied" label. |
| N4 | Without running, suites drift from the Waza schema and from the skill (new phrases in USE FOR, changed behaviour). | Waza schema versioning; `spec verify` design | Medium | **Pinned (2, 4)**: version pin; implement updates the suite whenever in-scope behaviour changes. **Revision 3:** V1 catches schema drift and V2 catches description-to-task coverage drift at every implement. |
| N5 | Is a deterministic, local `waza check` / `spec verify` "running them"? From source: `waza check` scores frontmatter compliance, token budget, eval presence and schema, with no agent; `spec verify` is deterministic unless `--semantic` (which calls a judge model). Waza also does a network update check unless `WAZA_NO_UPDATE_CHECK` is set. | Waza 0.38.9 source `cmd/waza/cmd_check.go`, `cmd/waza/cmd_spec.go`, `cmd/waza/root.go` | Medium | **Resolved by Sergio (01:10 BST): option (c).** Allowed with no model calls, never `--semantic`, `WAZA_NO_UPDATE_CHECK=1` (pin 4). |
| N6 | Allowing any Waza binary use invites drift towards model-calling commands: `--semantic`, `--judge-model`, `waza quality`, or a `mock` "smoke run" that is really a task run. | Waza 0.38.9 command list (`cmd_spec.go`, `cmd_quality.go`, `cmd_run.go`); Sergio's "no model calls" condition | High | **Pinned (4)** as a closed allowlist V1-V3, not a denylist; adversarial smoke `no-model-calling-waza-commands`. |
| N7 | A `--version` mismatch or an unset update check silently changes what "valid" means or adds a network call. | `cmd/waza/root.go` update check; pin 2 | Medium | **Pinned (2, 4)**: version recorded from `waza --version` and must equal 0.38.9 or validity is deferred; `WAZA_NO_UPDATE_CHECK=1` on every call (smoke `waza-update-check-off`). |
| N8 | Hand-authored `.results.json` fixtures could be tuned so graders pass trivially (the same Goodhart pressure as C4). | C4; Anthropic reference-solution guidance | Medium | **Pinned (7, 8)**: every checked task needs a negative control that must fail; fixture changes bump `suite_version` with a reason. |

Overlay: each counter that warns against a shipped artefact or instruction
becomes an adversarial smoke below.

### Challenge-success criteria (revision 3)

- C1 non-trivial counter: yes. N1 and N2 change what Exit may claim; N5
  needed a source read and a question to Sergio; N6 needed the Waza command
  list and the grader engine path read from source.
- C2 high-severity pinned or rejected with rationale: N1, N2 and N6 pinned;
  revision-1 Highs resolved, reshaped or moved out of scope with reasons above.
- C3 visible pins: section Pins, numbered 1-11.
- C4 scope intact: revision 3 widens only by Sergio's answer (V1-V2) and the
  deterministic-grader fixture check he made conditional (V3); still no task
  runs, model calls, CI job or dependency.
- C5 no implementation in this operation: no package, CI or repo change.
- Change-class stated: new-surface. Genesis Artifacts complete for the class:
  intent/scope/non-goals, three mermaid diagrams, interface sketch, cost
  note, acceptance, stop for approval.

## Behavioural contract (agent-spec)

deferred: agent-spec is neither declared nor available in this harness, and
this plan retires that gate. The Waza drafts above are the behavioural
proposal. Protected (gate) behaviours: design stops for approval; implement
blocks without approval; plans only in the resolved Atlas; help does not
mount; discussion has no implement authority; Autogenesis never runs suite
tasks and never makes a model call for evaluation.

## Evaluation plan

Deterministic smokes (primary, and the only evaluation Autogenesis runs) for
Phase 1 implement:

- `rg -n -i 'agent-spec|gherkin|\.feature' SKILL.md references/modules/*/SKILL.md`
  finds only historical notes allowed by the successor scenario.
- `rg -n -o 'waza [a-z]+' SKILL.md references/` yields only `check`, `spec`
  (as `spec verify`) and `grade` outside sentences that forbid a command.
- `rg -n -e '--semantic' -e '--judge-model' SKILL.md references/` finds only
  sentences that forbid them.
- Every allowlisted Waza command line in live instructions carries
  `WAZA_NO_UPDATE_CHECK=1` (or sits under a block that sets it).
- `rg -n '\bwaza-[a-z]' SKILL.md references/ .github/ apm.yml AGENTS.md CONTRIBUTING.md`
  is empty (no wrapper named anywhere).
- `rg -n -i 'waza|agent-spec' apm.yml apm.lock.yaml` is empty.
- `rg -n 'copilot-requests|COPILOT_GITHUB_TOKEN' .github/` is empty.
- `python3 -c` check that `invocation-contract.json` `behavioural_contract`
  values match every Arguments section.
- `python3 -m unittest discover -s scripts -p 'test_*.py'`, with a new parse
  test over every file in `suite-index.json`.
- Release readiness, dependency contract, store contract, source audit, both
  consumer profiles.

Model-free validity checks V1-V3: specified in Phase 1, first exercised in
Phase 2 on `evals/autogenesis/`. Agent evaluations: none run by Autogenesis.
Phase 2 authors the dogfood suite for the owner (intended: the on-demand
evaluator bot) to run.

## Adversarial scenario draft

Target file: `references/scenarios/waza-evaluation-adversarial-v1.yaml`
(successor of `specify-only-adversarial-v2.yaml`). Implement fills real
paths and commands; it may add smokes, never drop them.

```yaml
id: waza-evaluation-adversarial-v1
kind: skill-discipline
version: "1"
work_id: 2026-10-08-waza-evaluation
adversarial: true
packages:
  - id: subject
    root: "<candidate-root>"
    mode: mount
project:
  seed_knowledge: []
smokes:
  - id: autogenesis-never-runs-suite-tasks
    source: "Sergio 2026-10-08 01:06 BST: design, not run"
    cmd: "<every live line in SKILL.md and references/ naming 'waza run' (any executor, mock included) also says Autogenesis must not do it>"
    expect: {ok: true}
  - id: no-model-calling-waza-commands
    source: "Sergio 2026-10-08 01:10 BST: no model calls, no --semantic; N6 closed allowlist"
    cmd: "<every 'waza <subcommand>' in SKILL.md and references/ is check, spec verify or grade, unless the line forbids it; every line containing '--semantic' or '--judge-model' forbids it; no live 'waza grade' instruction omits --task or allows a prompt-grader task>"
    expect: {ok: true}
  - id: waza-update-check-off
    source: "Sergio 2026-10-08 01:10 BST: update check off; N7"
    cmd: "<every allowlisted waza command in live instructions runs with WAZA_NO_UPDATE_CHECK=1>"
    expect: {ok: true}
  - id: validity-is-not-behavioural-evidence
    source: "Revision 3 brief; N2"
    cmd: "<workflow-discipline and implement label the validity block (command, waza version, exit code, coverage) as not behavioural evidence>"
    expect: {ok: true}
  - id: no-model-calls-for-evaluation
    source: "Sergio pin 1; frugal stance"
    cmd: "! grep -rEq 'copilot-requests|COPILOT_GITHUB_TOKEN|waza ' \"$PKG_subject/.github\" && printf '{\"ok\":true}\\n'"
    expect: {ok: true}
  - id: upstream-waza-only
    source: "Sergio 2026-10-08: only waza; C1 Construct precedent"
    cmd: "! grep -rEq '\\bwaza-[a-z]' \"$PKG_subject/SKILL.md\" \"$PKG_subject/references\" \"$PKG_subject/.github\" \"$PKG_subject/apm.yml\" \"$PKG_subject/AGENTS.md\" \"$PKG_subject/CONTRIBUTING.md\" && printf '{\"ok\":true}\\n'"
    expect: {ok: true}
  - id: waza-not-an-apm-dependency
    source: "Format target, not package"
    cmd: "! grep -Eiq 'waza|agent-spec' \"$PKG_subject/apm.yml\" \"$PKG_subject/apm.lock.yaml\" && printf '{\"ok\":true}\\n'"
    expect: {ok: true}
  - id: waza-format-version-pinned
    source: "N4 schema drift"
    cmd: "grep -Fq '0.38.9' \"$PKG_subject/references/waza-authoring.md\" && grep -Fq 'schemaVersion' \"$PKG_subject/references/waza-authoring.md\" && printf '{\"ok\":true}\\n'"
    expect: {ok: true}
  - id: authored-suite-is-not-evidence
    source: "N2 exit-claim-equals-action"
    cmd: "<workflow-discipline and implement state that an authored suite is not behavioural evidence and carry run_status not-run-by-autogenesis>"
    expect: {ok: true}
  - id: no-autogenesis-run-evidence-fields
    source: "Sergio: remove run-evidence block"
    cmd: "<trials, k/n, CI and result sha appear in live instructions and templates only inside the supplied_results citation block>"
    expect: {ok: true}
  - id: supplied-results-carry-provenance
    source: "N3 evidence provenance"
    cmd: "<supplied_results format requires supplied_by, run_at with zone, suite commit, matches_authored, location, and the 'not produced by Autogenesis' label>"
    expect: {ok: true}
  - id: gate-tasks-have-grader-controls
    source: "N1 Anthropic reference solutions; TDD red-green"
    cmd: "<authoring guide requires a reference fixture and a negative control per gate task; deterministic graders are checked with waza grade (reference passes, negative fails); prompt-grader tasks are listed left_to_runner>"
    expect: {ok: true}
  - id: pass-bar-is-metadata-only
    source: "Revised C2"
    cmd: "<authoring guide records trials_per_task and the README pass rule as recommendations; no live instruction makes Autogenesis enforce them>"
    expect: {ok: true}
  - id: text-smokes-not-dropped
    source: "C3 keep deterministic layer; additive successor policy"
    cmd: "<every suite current at f901d0d is still current or has a successor in suite-index.json>"
    expect: {ok: true}
  - id: grader-change-bumps-suite-version
    source: "C4 Goodhart's law; versioned rubric"
    cmd: "<authoring guide requires a suite_version bump and recorded reason for any grader, threshold or prompt change>"
    expect: {ok: true}
  - id: judge-gets-original-input
    source: "Supplied run: a judge without the source cannot judge meaning"
    cmd: "<authoring guide requires prompt graders to embed the original input between BEGIN/END markers>"
    expect: {ok: true}
  - id: artefact-checks-read-files
    source: "Supplied run: text graders read only the chat reply"
    cmd: "<authoring guide requires file graders for produced content>"
    expect: {ok: true}
  - id: dot-folder-skills-configured
    source: "Supplied run: dot-folders skipped unless paths.skills is set"
    cmd: "<authoring guide requires .waza.yaml paths.skills when skills land in a dot-folder>"
    expect: {ok: true}
  - id: suites-safe-to-run
    source: "Revised C8: agent under test can read its environment"
    cmd: "<authoring guide requires local-only fixture remotes and forbids prompts that ask for push or credentials>"
    expect: {ok: true}
  - id: derived-skills-get-no-default-suite
    source: "Authoring vs derived boundary (root SKILL.md)"
    cmd: "<initialise and design do not add evals/ to a derived skill without an approved plan statement>"
    expect: {ok: true}
  - id: gherkin-gate-retired-cleanly
    source: "Legacy cutover rule: reject removed values, no alias"
    cmd: "<behavioural_contract: specify is rejected with a diagnostic; no live text requires agent-spec>"
    expect: {ok: true}
  - id: scenarios-parse
    source: "Inventory 2026-10-08: two scenario files are not valid YAML"
    cmd: "<every file in suite-index.json parses as YAML>"
    expect: {ok: true}
```

## Open questions for Sergio (prioritised)

1. ~~**Is a local Waza check "running them"?**~~ **Closed** (Sergio, 01:10
   BST): option (c). `waza check` and `waza spec verify` allowed with no
   model calls, never `--semantic`, update check off. Grader fixture checks
   follow the same condition and are possible model-free for deterministic
   graders (V3); `prompt` graders are left to the runner.
2. **Scope confirmation:** authored Waza suites replace the agent-spec gate;
   deterministic smokes stay and remain Autogenesis's only produced evidence.
3. **Description labels (Phase 2):** add `USE FOR:` / `DO NOT USE FOR:` to the
   Autogenesis description (638 of 1024 characters today) so trigger coverage
   is authorable? This changes the dispatch surface.
4. **Supplied red gate results:** record only, or should they also block an
   implement completion claim?
5. **Bundle:** should `evals/` (and `references/scenarios/`) ship in the APM
   package?
6. **genesis is undeclared:** list it only as a required skill in suite
   READMEs, or design declaring it?
7. **Fixture Atlas:** is a local file-backed store acceptable in fixtures?
8. **Hardening fold-in:** fix the unparseable current suite inside Phase 1, or
   as separate hardening?
9. **Version:** 0.9.0 (reasoning in the next section)?

Remaining open questions, in priority order: 2, 3, 4, 5, 6, 7, 8, 9.

Dropped since revision 1: eval token, manual CI job, budget cap, trials 3 vs 5
as run policy, unattended runs, wrapper visibility. Judge-model choice is now
README advice to runners.

## Version assessment

Still **0.9.0** for Phase 1. The change removes an accepted argument value
(`behavioural_contract: specify`), replaces a named gate, adds a shared
reference and work-node fields, and changes Exit evidence wording. On a 0.x
package that is a minor bump. The narrower scope removes the runtime and CI
surfaces but not the contract break. Revision 3 adds a closed allowlist of
model-free checks and an evidence sub-block inside the same Phase 1 cutover;
no further contract break, so still 0.9.0. Phase 2 (dogfood suite plus possible
description labels) would be 0.9.1 if it only adds `evals/`, or 0.10.0 if
the description labels change dispatch.

## Accepted risks

- Autogenesis produces no behavioural evidence itself; behaviour assurance
  depends on owners running suites (N2).
- Deterministic graders are checked against fixtures (V3), but fixtures are
  hand-authored and may not match what a real agent produces; `prompt`
  graders stay unchecked until someone runs them (N1, N8).
- Validity checks depend on Waza 0.38.9 being installed locally; when it is
  not, validity is deferred to structural checks (N7).
- Bundle leakage of `evals/` until open question 5 is settled.
- Waza format changes can stale the pin; a pin bump is a versioned design.

## Stop for approval

Explicit user approval is required before implement. Approval of this plan
covers Phase 1 only. No package, CI, tag, release or PR change was made in
this design, and no Waza command was run.

## Invocation receipt

```yaml
schema: autogenesis.invocation-receipt/v1
request_id: ag-2026-10-08-waza-design-r3
parent_request_id: ag-2026-10-08-waza-root
target: {skill: autogenesis, module: design, role: operation}
operation: design
status: completed
attempts:
  - number: 1
    outcome: completed
result:
  artifact: autogenesis/plans/2026-10-08-waza-evaluation.md
  disposition: awaiting-approval
  revision: 3
  closed_questions: [1]
evidence:
  loaded_entrypoints:
    - SKILL.md
    - references/modules/workflow-discipline/SKILL.md
    - references/modules/workflow-discipline/references/invocation-contract.md
    - references/modules/workflow-discipline/references/invocation-contract.json
    - references/modules/design/SKILL.md
    - references/skill-design-principles.md
    - references/modules/think-challenge/SKILL.md
    - references/modules/patterns/SKILL.md
    - references/modules/patterns/references/activation-card.md
    - references/modules/implement/SKILL.md
  external_skills: [genesis, atlas (mount, remember, work), think-challenge]
  source_reads: [waza 0.38.9 cmd/waza/cmd_check.go, cmd/waza/cmd_spec.go, cmd/waza/root.go, cmd/waza/cmd_grade.go, internal/graders/prompt_grader.go]
  user_decisions: ["2026-10-08 01:10 BST: allow waza check and spec verify with no model calls (no --semantic, update check off)"]
  substrate_note: "agent-spec unavailable; behavioural contract deferred"
  atlas_root: .atlas/github.com/sergio-sisternes-epam/autogenesis-atlas
  remember: true
  compile: true
gates: {Enter: pass, Change: pass, Exit: pass}
```
