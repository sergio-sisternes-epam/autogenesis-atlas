---
type: experience
title: Module migration release-candidate panel review
created: 2026-09-11
work_id: 2026-09-11-skill-module-invocation
status: recorded
subject: autogenesis
origin: derived
sensitivity: internal
description: Review the actual v0.5.0 migration and record one confirmed deployment-validation boundary blocker, two rejected findings and unchanged acceptance boundaries.
relates_to:
  - path: autogenesis/work/2026-09-11-skill-module-invocation.md
    kind: implements
  - path: autogenesis/experiences/2026-09-11-module-invocation-implementation.md
    kind: follows
  - path: autogenesis/experiences/2026-09-11-skill-module-pattern-implementation.md
    kind: related
  - path: autogenesis/experiences/2026-09-11-s8-self-review-diagnostic.md
    kind: related
  - path: autogenesis/plans/2026-09-11-s8-core-profile-self-application.md
    kind: related
---

# Module migration release-candidate review

## Atlas panel: needs rework

**One confirmed release-validation blocker remains.**

The current v0.5.0 source contains the 21-module migration and the draft S8
pattern. The panel retained one introduced deployment-validation defect after
fact-checking three proposed findings. It rejected the other two rather than
reporting legitimate installed paths or historical documentation as new bugs.
This is a validation-boundary failure, not demonstrated production exploitation.

| Lens | Blocker | Recommended | Nits | Takeaway |
|---|---:|---:|---:|---|
| atlas-contract | 0 | 0 | 0 | No introduced regression demonstrated in scoped Atlas-facing modules/templates |
| python-cli | 0 | 0 | 0 | Absolute installed-skill roots are permitted; proposed restriction rejected |
| skill-agent-contract | 0 | 0 | 0 | Proposed README version issue was unchanged historical guidance |
| security-gitops | 1 | 0 | 0 | Traversal-shaped ownership keys escape source/export boundaries |

### Top item

**Blocker: reject traversal-shaped root-owned deployment paths.**

Source location: `scripts/validate_consumer.py:620`, in the new
`validate_owned_files` function. The prefix helper at line 369 accepts:

```text
.agents/skills/<export>/../../review-sentinel.txt
```

`PurePosixPath.relative_to()` preserves the parent segments. Subsequent
`package_root / relative_path` and `export_root / relative_path` joins therefore
read outside both intended roots. A matching dependency hash and active-owner
record let both full validators accept the malformed ledger.

The coordinator reproduced this using the existing `ValidateConsumerTests`
complete package fixture, deployed all required assets and generated the lock
through the existing fixture helper. The intact control passed. Adding matching
sentinel files outside each respective root and the traversal key to the real
fixture ledger also passed `validate_lock()` and `validate_deployment()`.
No validation function was mocked. All files remained inside a disposable,
canonicalized temporary directory and were cleaned up.

**Follow-up:** reject malformed/traversal-shaped keys before accepting
ownership. Enforce resolved containment beneath each trusted root before
accessing files, including escape through filesystem links. Add a full-validator
negative regression retaining all required module/assets so missing-file errors
cannot mask the path failure.

This demonstrates a release-validation correctness defect. It does not show
credential disclosure, exfiltration, deployed-consumer corruption or that pinned
APM actually produces such keys. The finding was added as a local inline
annotation; no GitHub comment was published.

### Advisory recommendation

Do not release this candidate as-is. Correct the ownership-boundary defect
before relying on the release validator. The passing structural/regression
baseline does not retire the demonstrated adversarial failure.

<details>
<summary>atlas-contract - no introduced regression demonstrated</summary>

**Coverage:** compared work/run/activation templates with HEAD; inspected
atlas-migrate, discuss, validate-skill-import-links and
validate-okf-conformance entrypoints.

**Limitations:** no live Atlas/OKF mutation or broad compliance audit by the
reviewer. Its unrelated consumer import attempt exercised no product behavior
and was excluded from validation evidence.

**Findings:** no accepted findings after these scoped checks. This is not
closure of the earlier S8 diagnostic.
</details>

<details>
<summary>python-cli - absolute installed roots are not a regression</summary>

**Coverage:** source/trace request, receipt, resolved-path and argparse
validation; related regression suites; current scenario index.

**Findings:** no accepted findings. The reviewer proposed rejecting absolute
entrypoints outside the repository supplying the validator. The invocation
authority instead declares the actual loaded package root and entrypoint.
An installed consumer legitimately lives elsewhere. Structural trace
validation is not an attestation of file existence or execution.

**Limitations:** no live invocation proof; consumer deployment logic belonged
to the separate filesystem-boundary reviewer.
</details>

<details>
<summary>skill-agent-contract - historical migration guidance is not a new bug</summary>

**Coverage:** root/package identity, 21-module registry, progressive disclosure,
invocation/card/receipt/retry semantics, S8/B17 and release documentation.

**Findings:** no accepted findings. The proposed README line 89 finding was
rejected: the v0.4.0 Atlas storage-migration threshold already appears at
HEAD:README.md lines 51-52 and is unchanged context. A historical prerequisite
does not automatically become wrong when the current package version changes.

**Limitations:** no actual host discovery or live behavioral evaluation;
Atlas-facing modules and Python/scenarios were allocated to other reviewers.
</details>

<details>
<summary>security-gitops - one confirmed ownership-boundary blocker</summary>

**Coverage:** root-owned dependency hashes and active-owner records; disk
comparison and permitted Markdown rewriting; disposable traversal reproduction
independently extended to both full validators.

**Findings:** the added line in `validate_owned_files` accepts a traversal-shaped
relative path without enforcing containment. The full finding and narrow
follow-up are above.

**Limitations:** no production exploitation was demonstrated. Real APM consumer
installation was not rerun during this review; prior successful consumer
evidence remains separate.
</details>

## Scope, topology and attribution

The user requested review of the migration as the next release at 16:40 +01:00
on 2026-09-11. Reviewed tracked and untracked product changes against
`b6d8556e183c78cc0293feaa096e0db3b0cbdc01`, not only the tracked diff stat.
Moved entrypoints were compared with their old flat-file locations when
attributing regressions.

Four isolated read-only reviewer children had disjoint file ownership.
Atlas-contract used GPT-5.4-mini at low effort; the Python CLI, skill contract
and filesystem-boundary lenses used GPT-5.4 at low effort. All four lenses
were selected: always-on Atlas contracts, executable checker changes, skill/APM
contracts and new filesystem ownership behavior. No lens was skipped.
The coordinator fact-checked findings and remained the sole public writer.
A separate GPT-5.4 low-effort synthesizer consumed only validated receipts and
four deterministic checks. Its malformed first receipt received one bounded
retry; the accepted receipt passed JSON Schema and finding-provenance checks.
No review-process error was classified as a product finding.

Session evidence:
`files/module-migration-review-input.json` contains adjudicated receipts,
selection reasons and checks; `files/module-migration-review-synthesis.json`
contains the accepted synthesis. This page preserves the durable conclusions
independently of those session artifacts.

## Bounded deterministic evidence

| Check | Outcome | Limit |
|---|---|---|
| `python3 -m unittest discover -s scripts -p 'test_*.py'` | 71 passed | Existing local regression suite, not final CI |
| `python3 scripts/module_contract.py source --root .` | 21 modules, entrypoints and registry rows; 25 scenario files; no errors | Explicitly structural |
| Complete lock/deployment traversal fixture | Intact control and malformed traversal ledger both accepted | Confirms validation defect, not production exploitation |
| HEAD/current attribution and location checks | Two proposed findings rejected; retained location is added source | Prevents false positive migration findings |

## Remaining boundaries

- Product source was not edited. No commit, staging, push, release, tag,
  repository setting or global consumer change was performed.
- The reviewed store gitlink and root dependency lock were not advanced.
- The earlier S8 diagnostic and its D1-D8 design/remediation questions remain
  open. This narrower introduced-regression panel does not supersede or close
  that diagnostic.
- The approved direction is portable S8 core plus an Autogenesis profile.
  Its later implementation plan still awaits explicit implementation approval;
  this review request does not supply that approval.
- Final GitHub CI and the recorded live/discovery/behavioral acceptance gaps
  remain open. S8 stays draft; no active admission decision occurred.
