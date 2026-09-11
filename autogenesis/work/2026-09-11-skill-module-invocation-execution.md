---
type: document
title: Approved module invocation execution plan and delegation
created: 2026-09-11
work_id: 2026-09-11-skill-module-invocation
status: approved
description: Approved execution order, exclusive file ownership, model tiers, 21 module tasks, and fail-closed feasibility and acceptance gates.
relates_to:
  - path: autogenesis/work/2026-09-11-skill-module-invocation.md
    kind: implements
  - path: autogenesis/plans/2026-09-11-skill-module-invocation.md
    kind: derived_from
  - path: autogenesis/experiences/2026-09-11-module-invocation-implementation.md
    kind: related
---

# Implementation plan: skill-shaped modules and invocation discipline

Status: approved; execution explicitly requested on 2026-09-11 at 11:21 +01:00.
Work ID: `2026-09-11-skill-module-invocation`.
Execution: one existing branch, risk-based model delegation, one atomic cutover.

## Authority and approved planning assumptions

Design source, relative to the current worktree:
`.atlas/github.com/sergio-sisternes-epam/autogenesis-atlas/autogenesis/plans/2026-09-11-skill-module-invocation.md`.

The user selected one branch with risk-based delegation, then adopted the full
design as the implementation baseline, including proposed v0.5.0, no legacy
adapters, and the pre-migration deployment/discovery gate. Neither selection
authorises implementation before approval of this execution plan.

This approved execution companion adds order, ownership, and model routing;
it does not replace or silently amend the canonical Atlas design. The user
approved the execution plan through the plan approval control and subsequently
instructed: "ensure memory and proceed with implementation". The full planning
artifact is preserved here so execution does not depend on session history.

## Outcome and boundary

**Approved gate amendment:** the user's subsequent instruction is to check
locally and use GitHub CI as the final gate. This overrides the original
pre-migration all-target stop below. Local implementation proceeds; pinned
Linux and complete consumer validation are final CI obligations. Do not claim
CI passed or actual host discovery beyond observed evidence. Product pins and
scope stay unchanged. See the amendment in the canonical design.

Deliver one private APM root-skill package with 12 operation modules and nine
support modules at `references/modules/<name>/SKILL.md`. Preserve capabilities
and external invocation contracts while replacing the Autogenesis-owned live
path protocol with the designed request/card/receipt discipline.

Keep protected context parent-owned; preserve approval and subject-Atlas gates.
Use full root/operation cards and compact support cards, preserving absent,
off, on, and debug behaviour. Permit at most one retry after a transient,
known-repeat-safe failure; never reset the budget through parent replay.

Migrate all live repository consumers together; preserve all 12 historical
scenario bodies. Produce nine successor suites, two new invocation suites,
and their current/historical index. Adopt v0.5.0 on all current version surfaces.

No new invocation runtime, independent module exports, module dependencies,
marketplace structure, external repository changes, or global installations.
No tags, pushes, releases, repository-setting changes, or workflow dispatches.
No generated lock edits or store gitlink changes. A dependency, CI, or store
pointer change outside the design requires separate review, not worker discretion.

## Current evidence and prerequisites

- Product source remains unchanged; the Atlas submodule contains prior design
  and discussion edits. Preserve them and all unrelated user work.
- Design-stage offline baseline: 32 passing tests. Refresh before implementation;
  do not report that old result as evidence for the new source.
- `python3`, `apm`, `construct`, and `docker` are on PATH. Availability is not
  proof of the required versions, Docker daemon readiness, or working harnesses.
- Authentication clarification after the user challenged the initial assumption:
  `APM_READ_TOKEN` is the repository CI secret convention, not an intrinsic
  APM requirement for local work. Existing `gh` authentication can supply
  private access through APM's normal credential chain. The dependency-free
  local feasibility fixture needs no private credential. Confirm authentication
  only for actual private reads in their execution environment. Never expose
  raw credentials in prompts, artifacts, logs, or model receipts, or copy host
  credentials into an isolated container without an approved mechanism.
- Reviewed APM: 0.30.0, build `8c2e0d9`, Linux x86-64 archive SHA-256
  `8b84bebf19c350faf36d21aebb350dc656d04c0b7a1c2bf8ea35c0caa0e44bb9`.
  This macOS workspace's installed APM is not an equivalent verified artifact.
- Use an available Linux x86-64 container/environment with the verified artifact.
  Probe readiness after approval; do not assume that a Docker command means
  an execution environment is usable. No production migration before proof.
- The two APM profiles are `agent-skills` and
  `claude,codex,copilot,cursor,gemini,grok-build,kiro,opencode,windsurf`.
  Shared deployed directories do not prove identical host discovery.
- Agent-spec remains explicitly deferred. Do not author Gherkin or invent b- IDs.

## Delegation and model policy

Use file-scoped task agents in this worktree, not child sessions, separate
branches, or separate PRs. Implementation parallelism is unrelated to the
runtime module protocol: no spawn requirement is added to Autogenesis itself.
Cap active delegated agents at three, excluding the coordinator.

Model choices below are risk-based starting tiers, not a verified pricing
ranking. No current account-specific billing multipliers or measured savings
have been established. Use available billing/usage information at dispatch
when exposed; do not make unsupported dollar or percentage claims.

| Owner / task agent | Initial model and effort | Scope and reason |
|---|---|---|
| Coordinator, current session | Current GPT-6 Astra | Protocol decisions, high-risk modules, scheduling, integration, approval and evidence. Avoid another large-context planner. |
| APM feasibility specialist, `apm-expert` | `gpt-5.4`, high | Bounded pinned-artifact and discovery investigation; ambiguity warrants a stronger model. Run synchronously before fan-out. |
| Contract checker worker, `general-purpose` | `gpt-5.4`, high | Parent/context/lifecycle validation and non-tautological negative fixtures are semantic work, not mechanical migration. |
| Consumer worker, `apm-expert` | `gpt-5.4`, high | Ownership/provenance, transformed deployed assets, and frozen replay need APM expertise. Receive the probe receipt rather than repeating it. |
| Packaging then documentation worker, `general-purpose` | `gpt-5.4-mini`, medium | Bounded procedure-preserving moves, frontmatter, explicit reference bases, then docs/version alignment. Reuse the agent for the later stage. |
| Scenario worker, `general-purpose` | `gpt-5.4`, medium | Preserve adversarial coverage and separate behavioural proof from schema checks. Start after checker interfaces are frozen. |
| Final reviewer, `code-review` | `gpt-5.4`, high | One independent diff review focused on bugs, protocol regressions, omissions and weakened gates, not repeated design review. |

Six planned spawned agents, with a second turn for the packaging/documentation
worker. Do not create one agent per module or duplicate the prior design research.
Run commands directly where their output is needed; do not spawn an extra
reasoning agent merely to wrap a short test command.

Cost controls:

- Send a compact shared invariant brief, the canonical design path, exact task
  IDs/files, frozen interface sections, and acceptance commands. Workers read
  the relevant design slices and their target bodies, not the whole chat.
- Keep stable briefs and reuse worker context for same-scope repairs.
- One bounded correction on the assigned model for a concrete failure. If it
  still fails, or needs a new semantic decision, stop that owner and escalate
  with its diff and diagnostics. Do not silently loop or launch duplicate agents.
- Mini-worker semantic ambiguity goes to the coordinator; do not ask a small
  model to invent approval, retry, storage, or external-protocol policy.
- The implementation-worker repair budget is a project cost policy, separate
  from the product's two-attempt module invocation contract.
- Record reported model, task completion, corrective turns, and usage when the
  tools expose it. Unavailable cost data stays unavailable. Do not expand the
  task into a model benchmark.

## Shared worker contract

Every worker receives:

1. Current worktree and branch; canonical design and this execution-plan path.
2. The assigned task IDs and exclusive writable paths; everything else read-only.
3. P1-P9, source/history/external boundaries, no global operations, no secrets,
   no installs except justified missing prerequisites, and no commits/staging.
4. Frozen schema/registry/test interfaces and expected results for its scope.
5. A requirement to read each target body before editing it, preserve existing
   procedures, and use apply_patch for manual edits.
6. A completion receipt: changed paths, invariant mapping, exact commands and
   outcomes, unresolved blockers, and any required cross-owner change.

Workers must not edit another owner's files or fix unrelated findings. Send a
change request to the coordinator. The coordinator does not edit worker-owned
files until the worker returns ownership. Background agents are launched only
when the coordinator has concrete independent work to perform.

## Execution sequence and exit gates

### Phase 0: refreshed baseline and feasibility, before production edits

`execution-baseline` (coordinator):
Run `python3 -m unittest discover -s scripts -p 'test_*.py'` first.
Record Git state, historical-suite hashes, lock hash, module inventory, Python
version, and current prerequisite status in session evidence. Preserve prior
Atlas work. Distinguish pre-existing failures from regressions.

`deployment-probe` (APM feasibility specialist; depends on baseline):
Create a minimal disposable parent/operation/support/local-reference fixture.
Exercise both target profiles using the checksum-verified CI artifact, isolated
configuration, and disposable consumers. Do not change global marketplace
configuration. Confirm the single owned export, nested asset retention, local
reference resolution, and preservation after frozen replay.

Record an explicit per-target evidence matrix with artifact identity, fixture
identity, install/replay observations, and actual host discovery results.
Additional dependency skills are permitted. Compare deployed content using
documented APM transformations, not arbitrary byte-equality exceptions.
For actual discovery, inspect each supported host's catalogue or equivalent
observable discovery interface; a recursive filesystem listing is insufficient.

Exit: all required deployment and discovery evidence passes. A failed target,
missing host or unavailable verified execution environment blocks production
entrypoint changes. The absence of a particular token variable is not a failure;
authentication only blocks an actual required private read when no usable
authorised credential is available in its execution environment.
Ask for the missing prerequisite or an
explicit design amendment; never silently drop a target or weaken this gate.
Check independent prerequisites together rather than discovering them through
repeated expensive installation attempts. No extra workers launch while blocked.

### Phase 1: freeze the shared contract

`invocation-authority` (coordinator; depends on probe):
Repackage workflow discipline and author its invocation-contract.md/json.
Resolve the concrete request, receipt, trace-input, card, argument, and resource
reference shapes from the design. Define schema version, required/nullable
fields, state transitions, root bootstrap, parent transitions, redaction,
failure reasons, retry ownership, interrupted-state reconciliation, and external
skill correlation. Specify the evidence limits of a self-authored trace.

Freeze the 21-row registry shape, field names, checker CLI/output format,
scenario-index schema, and named test entrypoints before independent workers
implement consumers. Changes to this interface go through the coordinator and
are broadcast once, rather than patched independently by several agents.

`root-and-shared` (coordinator; depends on authority):
Update root routing and the shared reference templates, `references/README.md`,
and `references/templates/work-node.md`. Use explicit resolution bases.
Own the root `SKILL.md` version change to 0.5.0. Retain external skill schemas,
activation_card, B17, approval stops, and Atlas write-home.

### Phase 2: controlled fan-out

Launch checker, consumer, and packaging workers after Phase 1's interface freeze.
The coordinator concurrently migrates the five high-risk operation bodies.
Partial worktree states are expected during this phase but are not shippable.
Workers use isolated unit fixtures until integration is complete; do not change
another owner's source merely to make a partially migrated snapshot pass.

`contract-checker` (checker worker):
Own `scripts/module_contract.py`, `scripts/test_module_contract.py`, and
`scripts/test_source_contract.py`, including that file's version assertion.
Implement read-only `source --root` and `trace --input`, JSON stdout, useful
stderr diagnostics, explicit error exit and --help. Reuse existing helpers and
parsing conventions; do not assume a locally installed YAML library exists in
clean CI. A necessary new dependency requires an explicit justification.

Test exact module inventory, roles, entrypoints and references; scoped removal
of legacy live fields; card modes and redaction; protected context; approval;
attempt limits; unsafe/renamed/parent-amplified retries; interrupted state;
fabricated/card-only completion; and valid parent/support return. Positive
fixtures alone are insufficient. Test the source checker through the existing
unittest CI entrypoint, so no new CI job is required.

`consumer-contract` (consumer worker):
Own `scripts/validate_consumer.py`, `scripts/test_validate_consumer.py`,
`scripts/dependency_contract.py`, and `scripts/test_dependency_contract.py`.
Update the two direct-OKF caller paths without removing OKF. Validate exports
owned by Autogenesis using available provenance/ownership data, not a global
one-skill rule or unqualified name matching. Check all required nested assets,
unexpected owned exports, content and reference integrity, and lock ownership.
Validate again after frozen replay. Explicitly constrain allowed APM link
rewrites; don't tolerate arbitrary content changes. Add negative fixtures for
missing/corrupted assets, extra exports and replay corruption.

`module-*` tasks below:
One todo per module; group execution to save agent overhead. Every module has
standard name/description and string parent/role metadata, an Arguments section,
preserved prerequisites/procedure/output, correct references and invocation
behaviour. No forwarding wrappers. Move passive patterns resources under
`patterns/references/`, including the deprecated passive definitions.

| Module task | Role | Owner |
|---|---|---|
| module-workflow-discipline | support | Coordinator, Phase 1 authority |
| module-design | operation | Coordinator |
| module-initialise | operation | Coordinator |
| module-implement | operation | Coordinator |
| module-discuss | operation | Coordinator |
| module-atlas-migrate | operation | Coordinator |
| module-research | operation | Packaging worker |
| module-reflect-challenge | operation | Packaging worker |
| module-learn-skill | operation | Packaging worker |
| module-reevaluate | operation | Packaging worker |
| module-aware-runtime | operation | Packaging worker |
| module-wire | operation | Packaging worker |
| module-review-package | operation | Packaging worker |
| module-think-challenge | support | Packaging worker |
| module-think-grill | support | Packaging worker |
| module-think-ramble | support | Packaging worker |
| module-patterns | support | Packaging worker |
| module-validate-skill-import-links | support | Packaging worker |
| module-validate-progressive-disclosure | support | Packaging worker |
| module-validate-okf-conformance | support | Packaging worker |
| module-validate-gate-map-and-non-goals | support | Packaging worker |

The packaging worker owns only its listed old/new module bodies and patterns
resources. It preserves established semantics rather than redefining them.
Cross-cutting validator/pattern policy ambiguities return to the coordinator.

### Phase 3: scenarios and release-facing consumers

`current-scenarios` (scenario worker; depends on checker and an available slot):
Own only the 11 new scenario files and `references/scenarios/suite-index.json`.
Use the design's nine exact successor mappings and two invocation drafts.
Provide a mapping of old assertions to retained/replaced new assertions.
Keep all historical bodies byte-identical. Current selection must follow the
index, not a broad glob. Preserve approval, Atlas, provenance, disabled-card,
and sole-Gherkin-producer invariants. Coordinate named checker tests through
their owner rather than duplicating test implementation.

`docs-and-version` (reuse packaging worker after all its module tasks complete):
Own `AGENTS.md`, `README.md`, `CONTRIBUTING.md`, `CHANGELOG.md`, `apm.yml`,
`.github/ISSUE_TEMPLATE/bug_report.md`, and `scripts/test_release_readiness.py`.
Document the breaking cutover, new module layout and invocation semantics,
repository-only migration support, and current verification commands.
Keep current version surfaces at 0.5.0 without rewriting historical releases.
Align Unreleased migration notes and versioned release notes with the existing
release-readiness contract. Root and source-test versions remain their owners'
responsibility. Preserve dependency declarations and the generated lock.

Coordinator checks `scripts/release_readiness.py` and `scripts/release_notes.py`;
modify them only if required by the new current version surface, not merely
because the release number changed. CI workflow files and setup pins stay
unchanged unless an in-scope integration gap is demonstrated and approved.

### Phase 4: integrated verification and independent review

`integrated-validation` (coordinator; depends on all source owners):
Collect receipts and recover file ownership. Verify all 21 module moves,
root registry agreement, resource references, complete live-surface removal,
all 11 current suites and unchanged 12 historical bodies. Check references
to external skill paths and ordinary filesystem paths were not rewritten.
Ensure the source checker is actually exercised by existing CI tests.

Run targeted tests during each worker's scope; once integrated, run:

```text
python3 -m unittest discover -s scripts -p 'test_*.py'
python3 scripts/module_contract.py source --root .
python3 scripts/release_readiness.py
python3 scripts/dependency_contract.py
python3 scripts/store_contract.py
```

Then run source audit, root `apm lock` replay with lock byte equality, and both
full consumer profiles with private reads in isolated configuration according
to CONTRIBUTING.md. Root replay is not `--frozen`; consumer replay is.
Preserve exactly the documented dependency-anchor warnings; investigate any
additional warning rather than suppressing it.

`behaviour-evaluation` (coordinator; depends on integrated validation):
Run the design's real with/without-candidate tasks for approval refusal,
safe transient support retry and rejected legacy/context-override requests.
Observe actual effects/tool evidence, not merely generated receipts.
Run the disposable real design task, current happy/adversarial Construct
suites and the fixed 20-query trigger set (12 train, eight validation).
Retain the design thresholds: positive recall >=0.5 and false-positive rate
<0.5 on validation. Do not tune against the held-out set or report identical
baselines as measured improvement. Recheck candidate deployment/discovery
after the real migration; the minimal feasibility fixture is not final proof.

Discover the installed Construct CLI interface before composing its commands.
Missing evaluation capability or credentials blocks the relevant acceptance
gate; synthetic test success cannot substitute for live behavioural evidence.

`independent-review` (single code-review agent; depends on evaluation):
Review the integrated diff once for high-confidence regressions, focusing on
external invocation boundaries, protected context, retries, off/on/debug modes,
deployment ownership, historical coverage and missing consumer migrations.
Return findings with precise locations; no source changes or public comments.
Coordinator routes fixes to the owning worker or handles them after reclaiming
ownership, then reruns affected checks. Review findings cannot relax the design.

### Phase 5: durable handoff

`execution-exit` (coordinator; depends on review and required passing evidence):
Update the subject Atlas work/experience with decisions, changed surfaces,
genuine results and explicit remaining deferrals through Atlas discipline.
Compile memory; leave existing unrelated historical lint findings untouched.
Do not change the reviewed store gitlink to capture unreviewed memory changes.
Preserve a clear separation between package changes and store-local changes.

Clean only explicitly identified disposable fixtures/configuration. Check that
no credentials, generated deployments, or unrequested changes enter the source
diff. Keep a reviewable atomic change on this branch; no commit, push, PR,
tag or release action is implied by this plan.

## Dependency summary

Baseline -> feasibility -> invocation authority -> interface freeze.
After freeze: coordinator modules/shared root + checker + consumer + packaging.
Checker -> scenarios; packaging modules -> docs/version (same worker).
All source owners -> integrated validation -> live evaluation -> independent
review and corrections -> durable Exit.

Module-workflow-discipline is part of invocation-authority, not a second edit
pass. It and the other 20 module rows each have separate SQL completion records.

## Approval and blocking policy

The recorded approval authorises the bounded implementation above, not release or external
actions. Start with baseline and feasibility only. Do not spend on migration
workers while the pre-migration gate is blocked.

Completion requires the actual design acceptance evidence. Report a blocker
plainly if a required environment or evaluation is unavailable. An explicit
user-approved design amendment is the only route to changing that requirement.
