---
type: experience
title: Module invocation implementation and local integration
created: 2026-09-11
work_id: 2026-09-11-skill-module-invocation
implements: 2026-09-11-skill-module-invocation
closes: []
plan_path: autogenesis/plans/2026-09-11-skill-module-invocation.md
construct_eval: deferred
status: deferred
subject: autogenesis
description: Local 0.5.0 module cutover and independent review complete, with remaining live behaviour and final CI acceptance explicitly deferred.
relates_to:
  - path: autogenesis/work/2026-09-11-skill-module-invocation.md
    kind: implements
  - path: autogenesis/plans/2026-09-11-skill-module-invocation.md
    kind: records
  - path: autogenesis/work/2026-09-11-skill-module-invocation-execution.md
    kind: related
  - path: autogenesis/experiences/2026-09-11-module-invocation-design.md
    kind: follows
---

# Module invocation implementation

## Approval and decisions

Following the blocker discussion, the user approved local implementation and
local checks with GitHub CI as the final gate. This supersedes the earlier
all-host pre-migration stop. No original product invariant was waived; the
canonical design now distinguishes local evidence from final CI acceptance.

The user selected one branch with risk-based delegation rather than independent
worktrees/PRs, then adopted the full design including v0.5.0, no adapters, and
the pre-migration feasibility gate. The plan approval control recorded approval.
At 2026-09-11 11:21 +01:00 the user explicitly requested:
"ensure memory and proceed with implementation".

The full approved execution plan is stored in this work cluster, linked above.
The current GPT-6 Astra coordinator owns protocol semantics and integration.
GPT-5.4-mini handles bounded packaging/documentation; GPT-5.4 handles the APM
probe, checker, consumer, scenarios and independent review at the specified
efforts. Six planned agents, maximum three concurrent delegates, exclusive file
ownership, scoped context, one bounded correction before escalation. These are
risk-based tiers, not a measured claim about prices or savings.

## Refreshed baseline

The existing offline suite ran before implementation: 32 tests passed in
1.296 seconds. Actual `python3` reports 3.9.6, not the repository's required
3.12; this result is useful baseline evidence, not the pinned-runtime gate.
The APM specialist must identify a compliant runtime without global changes.

Git status showed only the already-dirty subject Atlas submodule. Source
inventory includes the 12 old operational paths and nine loose internal
modules, plus passive patterns assets. Historical scenario and lock hashes
were captured in session evidence.

Root lock SHA-256:
`671d46bdda0f2c6192c3b0b446677f069620e03209de29a1fdefe3ddf2538bdc`.

Raw baseline artifact:
`/Users/sergio_sisternes/.copilot/session-state/aa9a2f4d-9638-4c14-a557-c1cf6a900529/files/implementation-baseline.txt`.

Coordinator follow-up resolved local Python through `uv python find 3.12`
without installing anything. Existing Python 3.12.13 ran the 32 offline tests
successfully in 1.116 seconds. This resolves the local interpreter prerequisite,
not the missing Linux runtime. Evidence:
`/Users/sergio_sisternes/.copilot/session-state/aa9a2f4d-9638-4c14-a557-c1cf6a900529/files/implementation-baseline-python312.txt`.

## Historical feasibility checkpoint

The initial bounded probe ran through an `apm-expert` task with requested model
`gpt-5.4`, reasoning effort `high`. No migration worker launched. No model
billing or independently confirmed provider model identity was returned.

The specialist downloaded the approved public Linux x86-64 APM 0.30.0 archive.
SHA-256 matched
`8b84bebf19c350faf36d21aebb350dc656d04c0b7a1c2bf8ea35c0caa0e44bb9`.
The extracted binary is a Linux x86-64 ELF executable. Execution was NOT RUN:
the local Docker command is a Podman wrapper whose configured connection
refused the server request. No host runtime was started or reconfigured.
Installed macOS APM still cannot substitute for execution of the pinned artifact.

The isolated fixture contains a root skill, operation and support SKILL.md
files, and module-local references. Copilot CLI 1.0.83's non-billable
`skill list --json` discovered `phase0-probe-root` without listing the nested
`probe-operation` or `probe-support`. This is actual Copilot discovery evidence,
not APM installation, frozen replay, or agent-followed invocation evidence.
The command also emitted an unrelated inherited-skill YAML parse diagnostic;
the fixture observation is not a claim that all global skills are healthy.

| Target | Pinned deployment / frozen replay | Actual discovery |
|---|---|---|
| agent-skills | NOT RUN: Linux execution unavailable | N/A: deployment profile, not a separate host |
| copilot | NOT RUN: Linux execution unavailable | Root-only fixture discovery observed |
| claude, codex, cursor, gemini | NOT RUN: Linux execution unavailable | NOT RUN: host executables unavailable |
| grok-build, kiro, opencode, windsurf | NOT RUN: Linux execution unavailable | NOT RUN: host executables unavailable |

`APM_READ_TOKEN` was unset. Initially this was incorrectly treated as a blocking
prerequisite; see the authentication correction below. The original full-target
gate was unmet at this checkpoint. Work was deferred at Phase 0 until the
subsequent explicit local/CI amendment recorded above.
Remaining prerequisites: an executable Linux x86-64 environment for the verified
artifact and actual discovery evidence for the other eight supported hosts.
An existing configured Podman machine is not proof that it is running or can
execute x86-64 binaries.

Raw specialist report:
`/Users/sergio_sisternes/.copilot/session-state/aa9a2f4d-9638-4c14-a557-c1cf6a900529/files/module-feasibility-report.md`.

Verified archive and minimal fixture are retained under the session's named
`files/phase0-deployment-probe/` directory for a resumed probe. They are not
committed package assets. Full acceptance is neither inferred from this partial
evidence nor silently narrowed to Copilot.

## Authentication correction

The user asked why APM_READ_TOKEN was needed when their account already has
read access. The agent had conflated the repository's CI secret convention
with local authentication and had imposed an unnecessary prerequisite on a
dependency-free local fixture.

The installed APM 0.30.0 `core/auth.py` documents and implements the active
gh CLI account fallback after explicit token variables. Repository CI explicitly
requires its named APM_READ_TOKEN secret and passes it to APM's per-org variable;
that CI configuration remains unchanged. Local APM does not intrinsically
require that variable. Authentication is needed only for actual private reads,
and the existing authenticated client can be used without displaying its token.

Two live `gh api repos/...` metadata calls returned `private: true` and
`permissions.pull: true` for autogenesis-atlas and atlas-marketplace. No
credential value was requested or displayed. This demonstrates those host-side
reads, not every private dependency or future container authentication.

Remove the named-token absence from the Phase 0 blockers. A later isolated
environment must have a usable authorised authentication path when it performs
private reads; host login is not automatically inherited. No raw token should
be copied into reports, agent context or container images.

## Local implementation and integration

The package now has one root and all 21 parent-routed module entrypoints.
Central prose and JSON declare arguments, protected context, visible request
cards, receipts, lifecycle and bounded retry. No compatibility wrappers or
independent module exports were introduced.

The packaging/documentation worker used GPT-5.4-mini; protocol, checker,
consumer and scenario workers used GPT-5.4. The coordinator reclaimed completed
files and corrected semantic drift in mechanical moves: protected fields had
appeared as arguments, ambiguous argument aliases remained, B17 duplicated an
old schema, and core callers lacked canonical argument bindings. Reevaluate's
advisory candidate was distinguished from an approved formal design and its
challenge now invokes support rather than silently switching operations.
These are observed delegation lessons, not new normative design decisions.
Tool-reported model labels are recorded; billing and savings are unavailable.

The first integrated Python 3.12.13 suite passed 50 tests. Source validation
reported 21 modules, 21 registry rows, 21 entrypoints and 23 scenario files.
Release, dependency and store checks passed. APM source audit passed for 51
tracked existing files plus 41 newly added files explicitly audited outside
the Git index. Audit log:
`/Users/sergio_sisternes/.copilot/session-state/aa9a2f4d-9638-4c14-a557-c1cf6a900529/files/local-source-audit.txt`.

The scenario worker reports 79 current-index smoke commands passing. These
are command assertions, not Construct or live model behaviour evidence.
Integration review then found checker gaps for empty completion evidence,
resolved-target mismatches, malformed nested JSON, interrupted attempt history
and approval before actual implement attempts. A bounded correction is in
progress at that checkpoint; the first integrated result was not final acceptance.

### Settled local evidence before independent review

The checker correction is complete. It rejects malformed nested JSON without
tracebacks, correlates resolved entrypoints and loaded evidence, requires
approval before actual implement attempts, retains blocked execution history,
and preserves the durable deferral and discussion boundaries. All eight
pre-existing source/CI protection tests were restored alongside the new source
checks; replacing them wholesale had been an integration regression.

Real APM exercise exposed YAML `null` and long complex-key forms in deployment
hash maps; the consumer parser now handles them with regression tests. The
coordinator also closed an omission gap: every source `references/` asset must
be deployed, even if it is absent from both ownership/hash maps.

The settled Python 3.12.13 suite passed **65 tests**. Source validation, release
readiness, dependency and store checks passed. Historical YAML files and root
lock are unchanged. Source audit passed again for 51 tracked existing files
and all 41 new source files; this explicitly avoids Git-index-only omission.
Positive and malformed trace CLI fixtures respectively returned pass and JSON
failure with exit 1. These generated fixtures are not live execution receipts.

Local APM **0.30.0** ran through its explicit user-local executable with isolated
HOME/APM configuration and normal gh authentication. Root `apm lock` replay
used an isolated copy of the current manifest, root skill and lock, not
`apm install --frozen`; the resulting lock was byte-identical at the SHA above.
Both actual consumer profiles then installed the settled worktree, validated
ownership/assets, replayed frozen and passed APM audit:

| Consumer profile | Frozen consumer lock SHA-256 | Result |
|---|---|---|
| `agent-skills` | `a8b9974ab7042d8765ed055e5ac7976611a3a1a63ce3a19f2c338a3d50611982` | pass |
| `claude,codex,copilot,cursor,gemini,grok-build,kiro,opencode,windsurf` | `ae4025c351f26fca7b564b96ad59764aed7662430cfce4517f4563d9d17afb5d` | pass |

Persistent evidence directory:
`/Users/sergio_sisternes/.copilot/session-state/aa9a2f4d-9638-4c14-a557-c1cf6a900529/files/final-local-ZFSzi8`.
Files: `root-replay.log`, `consumer-agent-skills.log`,
`consumer-stable-runtimes.log`, `source-audit.log`, `valid-trace.json`,
`valid-trace-result.json`, `invalid-trace.json`, `invalid-trace-result.json`,
`invalid-trace-diagnostic.txt`.

An earlier stable-runtime probe reported Kiro drift in `module_contract.py`
while source was still changing. Its cause remains undetermined; concurrent
source edits are a hypothesis, not proof of transient APM failure. It did not
recur in the settled-source validation.

Actual Copilot discovery in the specialist's isolated migrated consumer listed
the single Autogenesis top-level root, not its nested module paths. Dependency
`think-challenge`, `think-grill` and `think-ramble` roots were distinguished by
their exact top-level locations; their names are not evidence of leaked
Autogenesis module exports. Other hosts' actual discovery remains unobserved.

One independent GPT-5.4 high-effort internal diff reviewer was assigned.
This is the approved single-agent implementation review, not a published PR
panel; no PR exists and no public comments are authorised.

### Independent review and final local handoff

The reviewer returned two medium findings: current indexed scenario YAML bodies
were omitted from reference validation, and blanket reference exemptions hid
removed owned paths and nonexistent scenario-index links. Both were corrected.
The source checker now scans only indexed current YAML bodies for literal
package asset references, keeps historical bodies out of the live scan, rejects
missing index links, and narrowly permits the five external Atlas path names
actually used. Three regression tests cover both failures and the external
contract boundary.

After these corrections, **68 tests passed** on Python 3.12.13. Source checking
and targeted APM audits passed. Both consumer profiles were rerun against the
final source and again passed install, frozen replay, ownership/content checks
and audit:

| Final consumer profile | Frozen consumer lock SHA-256 | Result |
|---|---|---|
| `agent-skills` | `3d4bb2e18d3098fc5334623000a6010cd68f2feb0c603eff4f86523914c2787d` | pass |
| stable runtimes listed above | `dd3eff5c7deb2b4ab749c9684ad643c36412159386b11d3517896c80baff9e2a` | pass |

Additional evidence files in the same directory:
`post-review-tests.log`, `post-review-source.json`, `post-review-audit.log`,
`post-review-agent-skills.log`, `post-review-stable-runtimes.log`,
`copilot-discovery.json`. Consumer lock hashes are stable within each frozen
replay, not a promise that separate disposable installations have identical
locks.

The scoped Copilot discovery result was persisted before removing the four
specialist-created disposable probe directories. Its inherited global skill
loading still emitted the known, unrelated marketplace-review YAML diagnostic;
no global skill was modified and no claim of global catalogue health is made.
The verified Phase 0 archive and named final evidence/configuration remain in
session artifacts for the pending acceptance work. No product scratch files
remain.

Local source implementation and review are complete. Overall acceptance stays
deferred: final GitHub CI is not run, other hosts' actual discovery is not
observed, and live Construct/paired/trigger evaluations are not performed.
Existing deterministic CI is not claimed to run those live evaluations
automatically. No commit, staging, push, tag, release, settings change, global
consumer update or store gitlink update was performed.

## Changed files

All paths below are relative to the package root. Moves remove the old file
and create the new file; none are compatibility adapters.

| Removed operation source | Added module entrypoint |
|---|---|
| `references/paths/atlas-migrate.md` | `references/modules/atlas-migrate/SKILL.md` |
| `references/paths/aware-runtime.md` | `references/modules/aware-runtime/SKILL.md` |
| `references/paths/design.md` | `references/modules/design/SKILL.md` |
| `references/paths/discuss.md` | `references/modules/discuss/SKILL.md` |
| `references/paths/implement.md` | `references/modules/implement/SKILL.md` |
| `references/paths/initialise.md` | `references/modules/initialise/SKILL.md` |
| `references/paths/learn-skill.md` | `references/modules/learn-skill/SKILL.md` |
| `references/paths/reevaluate.md` | `references/modules/reevaluate/SKILL.md` |
| `references/paths/reflect-challenge.md` | `references/modules/reflect-challenge/SKILL.md` |
| `references/paths/research.md` | `references/modules/research/SKILL.md` |
| `references/paths/review-package.md` | `references/modules/review-package/SKILL.md` |
| `references/paths/wire.md` | `references/modules/wire/SKILL.md` |

| Removed support source | Added module entrypoint |
|---|---|
| `references/modules/patterns.md` | `references/modules/patterns/SKILL.md` |
| `references/modules/think-challenge.md` | `references/modules/think-challenge/SKILL.md` |
| `references/modules/think-grill.md` | `references/modules/think-grill/SKILL.md` |
| `references/modules/think-ramble.md` | `references/modules/think-ramble/SKILL.md` |
| `references/modules/validate-gate-map-and-non-goals.md` | `references/modules/validate-gate-map-and-non-goals/SKILL.md` |
| `references/modules/validate-okf-conformance.md` | `references/modules/validate-okf-conformance/SKILL.md` |
| `references/modules/validate-progressive-disclosure.md` | `references/modules/validate-progressive-disclosure/SKILL.md` |
| `references/modules/validate-skill-import-links.md` | `references/modules/validate-skill-import-links/SKILL.md` |
| `references/modules/workflow-discipline.md` | `references/modules/workflow-discipline/SKILL.md` |

Patterns assets moved from `references/modules/patterns/` into its
`references/` child, preserving the same suffixes: `activation-card.md`,
`template.md`, `deprecated/panel-review.md`, `deprecated/triage-panel.md`.
B17's live contract now references the sole invocation authority.

Added authority:
`references/modules/workflow-discipline/references/invocation-contract.md`
and `references/modules/workflow-discipline/references/invocation-contract.json`.

Edited root/shared/docs:
`SKILL.md`, `apm.yml`, `AGENTS.md`, `README.md`, `CONTRIBUTING.md`,
`CHANGELOG.md`, `.github/ISSUE_TEMPLATE/bug_report.md`,
`references/README.md`, `references/activation-plan-template.md`,
`references/run-record-template.md`, `references/challenge-success-criteria.md`,
`references/templates/work-node.md`.

Added checker:
`scripts/module_contract.py`, `scripts/test_module_contract.py`.
Edited checks:
`scripts/test_source_contract.py`, `scripts/validate_consumer.py`,
`scripts/test_validate_consumer.py`, `scripts/dependency_contract.py`,
`scripts/test_dependency_contract.py`, `scripts/test_release_readiness.py`.

Added scenario files under `references/scenarios/`:
`suite-index.json`, `autogenesis-adversarial-v3.yaml`,
`atlas-migrate-activation-adherence-v3.yaml`,
`discuss-activation-adversarial-v3.yaml`,
`activation-card-extend-adversarial-v2.yaml`,
`atlas-storage-semantics-adversarial-v2.yaml`,
`catalogue-review-gate-adversarial-v2.yaml`,
`patterns-as-genesis-extension-adversarial-v2.yaml`,
`patterns-module-adversarial-v2.yaml`, `specify-only-adversarial-v2.yaml`,
`module-invocation-adversarial-v1.yaml`, `module-invocation-happy-v1.yaml`.
All 12 historical YAML files remain byte-identical.

The root lock hash remains unchanged; no store gitlink update was made.
The Atlas has additional local memory changes, separate from package source.

## Follow-up discussion: module as a reusable pattern

The user asked whether Autogenesis understands modules and whether the concept
should become a pattern alongside Activation Card.

Observed distinction: the local v0.5.0 candidate explicitly defines modules in
its router, workflow authority, entrypoints and checks. Initialise already
includes parent-routed modules in its design fusion. However, the pattern
injector still lists only B17 ACTIVATION CARD, so module composition is not
yet exposed as a named catalogue choice. The installed v0.4.3 skill remains
unchanged.

Recommendation, not an approved change: document a draft **Parent-routed Skill
Module** composition profile for reusable skill design. It would describe
skill-shaped entrypoints, declared inputs, optional local references, parent
routing/context ownership, operation/support roles, and reference to the
parent's invocation contract. It must not duplicate the protocol schema or
export nested modules as catalogue roots.

Keep three concerns distinct: module is the structural unit; invocation is
the call and its inputs/context/result evidence; Activation Card is the visible
request interface. B17 remains active, not a deprecated or legacy mechanism.
Its existing identity does not need renumbering because a structural profile
is introduced.

Before admitting a new Autogenesis pattern, compare the candidate with the
relevant read-only Genesis patterns and composition modes. If composition
already expresses it, retain a named profile rather than another overlapping
catalogue. If a genuine extension remains, admit it as draft first; repeated
known-use evidence is required for active status. Twenty-one modules within
one package do not alone establish repeated independent adoption. No pattern
ID or active status is assigned, no product source is changed, and the user
has not yet approved this follow-up.

## Remaining evaluation limits

defer: Construct is installed as a command but `construct --help` fails with
`ModuleNotFoundError: construct`; no justified installation source/version has
been established. With/without-candidate live behaviour exercises, the real
design exercise, and the 20 labelled trigger cases have not run. No trigger
scores or behavioural improvement are claimed.

Final GitHub CI and other-host discovery remain pending. Approval does not
authorise tags, pushes, releases, settings changes, global consumer updates,
or modification of the reviewed store gitlink.
