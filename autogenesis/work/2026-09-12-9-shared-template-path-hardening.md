---
type: work
title: Shared template path resolution hardening
created: 2026-09-12
work_id: 2026-09-12-9-shared-template-path-hardening
status: draft
external_ref: "https://github.com/sergio-sisternes-epam/autogenesis/issues/9"
description: Generalize regression prevention for package-shared template references after two module-relative paths were missed during the v0.5.0 migration review.
relates_to:
  - path: autogenesis/experiences/2026-09-12-pr7-missed-shared-template-paths.md
    kind: derived_from
  - path: autogenesis/work/2026-09-12-9-shared-template-path-hardening-protostar.md
    kind: related
  - path: autogenesis/work/2026-09-11-skill-module-invocation.md
    kind: follows
---

# Shared template path resolution hardening

## Scope

Audit live module resource references and generalize deterministic source
coverage so package-shared assets use `<skill_root>/...`, module-local assets
resolve from the module root, and sibling procedures resolve through the parent
registry.

## Status

The two concrete PR #7 defects were fixed before merge. This follow-up is
regression hardening tracked by GitHub issue #9, not a claim that the merged
package still contains those broken references.

## Outcomes

- [Review experience](../experiences/2026-09-12-pr7-missed-shared-template-paths.md)
- [Forming hardening action](2026-09-12-9-shared-template-path-hardening-protostar.md)

## Related

- GitHub issue: https://github.com/sergio-sisternes-epam/autogenesis/issues/9
- Originating pull request: https://github.com/sergio-sisternes-epam/autogenesis/pull/7
