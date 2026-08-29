# Autogenesis skill process memory (Atlas)

Subject Atlas for the **autogenesis** skill.

## Layout

- [autogenesis/](autogenesis/) — **Autogenesis space** (all Autogenesis-authored experiences, decisions, work, plans)
- `templates/` — promote templates (shared)
- `staging/` — short-lived buffer (must be empty for green compile)

On **other** target skills, the same `autogenesis/` prefix is used so the skill’s own root-level memory is not mixed with Autogenesis-authored pages.

## Authoritative rules

- Process memory + design plans → Atlas only
- Plans → `autogenesis/plans/<work_id>.md` (`type: plan`)
- Missing Atlas → inform user; offer initiate (and migrate if okf-wiki present)
