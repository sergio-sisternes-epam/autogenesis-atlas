---
type: protostar
title: Prove nested module deployment and routing
created: 2026-09-11
work_id: 2026-09-11-skill-module-invocation
status: open
kva: forming
growth: true
star_kind: probe
stage: implement
artifact: autogenesis/plans/2026-09-11-skill-module-invocation.md
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/experiences/2026-09-11-module-invocation-implementation.md
    kind: related
  - path: autogenesis/work/2026-09-11-skill-module-invocation.md
    kind: implements
  - path: autogenesis/plans/2026-09-11-skill-module-invocation.md
    kind: related
  - path: autogenesis/discussions/2026-09-11-module-model-walkthrough.md
    kind: derived_from
---

# Bounded loader experiment

The walkthrough has not demonstrated runtime discovery behaviour. A future
approved disposable fixture should contain one parent SKILL.md, one operation,
one support module, and one module-local reference.

Observe whether the supported APM/harness deployment preserves all resources,
exposes only the parent as an intended catalogue entry, resolves module-local
references correctly, and preserves the active operation during support loads.
An accidental direct operation activation must fail closed without parent
context and workflow prerequisites.

This experiment is not run or approved by the request to show the idea.
Keep a catalogue compatibility failure distinct from an agent's failure to
follow module instructions. Neither paper traces nor successful Markdown
compilation establish either behaviour.

## Compatibility cases added by the terminology discussion

The same bounded fixture should exercise the supported reader/writer
combinations before any non-breaking migration claim:

| Input or consumer | Required outcome |
|---|---|
| Old user vocabulary and module id | Same canonical module and gates |
| Old card consumed by a new reader | Same meaning after normalisation |
| Old reader consuming default new-release output | Legacy representation remains accepted |
| Explicitly enabled new output consumed by a new reader | Same context and authority |
| Contradictory legacy and new fields | Explicit rejection before execution |
| Legacy entrypoint file | Actual canonical body loaded; honest load evidence |
| activation_card absent, off, on, or debug | Existing behaviour preserved |
| Legacy request to implement without approval | Still blocked |

These are proposed compatibility cases, not completed tests. Exact schema
names, negotiation mechanism, and retirement policy require formal design.

## User-selected migration direction

The preceding adapter and legacy-default-output discussion was an agent
recommendation, not an approved policy. On 2026-09-11 the user selected:

> Migrate all supported consumers together and remove the legacy surface in the first release

This selects a coordinated cutover, not a backwards-compatible release for
unmigrated clients. Do not retain adapters or aliases solely on the authority
of the earlier recommendation. Historical evidence remains historical; it is
not a live compatibility surface.

The supported-consumer boundary must now be named before formal design can
claim complete coverage. In-repository surfaces and external skill repositories
are different scopes; installed/global consumers are not implicitly authorised
for updates. The old compatibility matrix above remains discussion history,
not the final acceptance matrix for the selected cutover.

## Supported-consumer scope decision

On 2026-09-11 the user selected:

> All live consumers maintained in the Autogenesis repository (Recommended)

The coordinated cutover covers this repository's live root and module
instructions, templates, documentation, checks, and current scenario contracts.
External skill repositories and installed/global consumers are excluded.
Calls to external root skills must still follow those skills' existing
contracts; their internal paths must not be mechanically rewritten.

The cutover policy and scope are settled. This page remains forming solely
because the complete deployment/consumer probe has not yet passed.

The formal plan adopts this as its first implementation gate after approval.
Installed APM 0.30.0 source was inspected and supports native-root nested asset
copying without references-based child promotion. That is not a completed
deployment or actual harness-discovery probe. Use the plan's selected cutover
acceptance, not the obsolete adapter matrix above.

## Approved implementation probe progress

After explicit implementation approval, the bounded Phase 0 probe verified the
Linux APM archive hash and observed Copilot CLI 1.0.83 discovering only the root
of a disposable root/module fixture. It did not execute the pinned Linux binary,
run APM deployment/frozen replay, or prove discovery for the other eight hosts.
The configured Podman connection refused access and APM_READ_TOKEN was unset.
Python 3.12 was found through uv and the local baseline completed.

The [implementation experience](../experiences/2026-09-11-module-invocation-implementation.md)
records the exact partial evidence and blockers. No production file moved.
The probe is still open; evidence for one host does not settle the approved
all-target acceptance gate.
