---
type: document
title: Uniform module packaging with distinct roles
created: 2026-09-11
status: settled
kva: alive
stage: discussion
artifact: SKILL.md
origin: derived
sensitivity: internal
relates_to:
  - path: autogenesis/discussions/2026-09-11-skill-module-evolution.md
    kind: derived_from
  - path: autogenesis/discussions/2026-09-11-module-activation-boundary.md
    kind: follows
---

# Scope of module packaging

The user selected "Use one packaging format for both, retaining distinct roles
(Recommended)" on 2026-09-11.

The direction is one packaging format with distinct capability and support
roles. Capability modules represent operations such as design and implement;
support modules provide workflow discipline, validators, and shared material.
Uniform packaging must not make support loads equivalent to workflow
transitions or independently expose helpers.

Converting paths alone was considered but not selected. Uniform packaging
does not require turning passive reference documents or templates into modules.
The exact role vocabulary and metadata representation are not specified by
this pin. No formal design or implementation is authorised.
