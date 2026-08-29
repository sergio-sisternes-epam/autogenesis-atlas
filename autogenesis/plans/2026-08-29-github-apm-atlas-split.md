---
type: plan
title: "Design — GitHub APM packages; Atlas split to <repo>-atlas"
created: "2026-08-29"
work_id: "2026-08-29-github-apm-atlas-split"
status: designed
change_class: new-surface
subject: autogenesis
kva: alive
description: "Central hub. Publish skills to GitHub. Extract every skill Atlas to a sibling <repo>-atlas. Local tree always wins over existing remotes."
plan_path: autogenesis/plans/2026-08-29-github-apm-atlas-split.md
catalogue_review: n/a
catalogue_review_rationale: "Release/migration topology, not a new agent primitive."
behavioural_contract: deferred: specify after approval if mount-on-install is in-scope behaviour
relates_to:
  - path: work/2026-08-29-github-apm-atlas-split.md
    kind: implements
---

## Intent + scope

Autogenesis is the **only plan hub**. Atlas stores across **all** skills are extracted. Named skills become GitHub APM packages. Existing GitHub repos (including `sergio-sisternes-epam/atlas`) are **overwritten from this machine**. Ours always wins.

### Skill packages (GitHub + APM)

| GitHub repo | APM package(s) |
|-------------|----------------|
| `atlas` | atlas |
| `autogenesis` | autogenesis |
| `discuss` | discuss |
| `construct` | construct |
| `think` | think-challenge, think-grill, think-ramble (one repo, three package entrypoints) |

Org default: `sergio-sisternes-epam` unless login shows another.

### Atlas repos (every skill that has `references/atlas`)

Pattern: `<skill-repo>-atlas` as a **dedicated** Atlas (empty subpath).

Known stores today: agent-brain, agent-spec, atlas, autogenesis, construct, discuss, gamma, knowledge-crawl, medium, portfolio, skill-feedback, visual, apm.

Think trio: **one** `think-atlas` (one Atlas root per git repo).

After extract, the skill repo keeps `references/atlas` only as an `atlas mount` of that dedicated repo (submodule), not as the canonical copy.

### Ours always wins

Local `/home/workdir/.grok/skills/<name>` (and extracted Atlas trees) are the source of truth. If `sergio-sisternes-epam/<repo>` already exists, update it to this tree (force-with-lease only if history must be kept; otherwise replace default branch content). Do not merge remote-only commits over local.

### Transport (this harness)

No `gh` login and no durable clone. The GitHub connection can `create_repository`, `push_files` (batch commit), and `create_or_update_file` (single path; SHA required when replacing). Read-back is `get_file_contents` / `get_repository_tree` only.

After a check-in this session is **disconnected** from that remote. Local skills stay the working tree. Remotes are snapshots. `atlas mount` / submodules belong on a later git machine, not after these API writes.

Ours wins: upload local bytes. Do not merge remote-only history. Force-with-lease does not apply; there is no local git remote.

## Non-goals

Nested-group URI work. Rewriting query engines. Publishing every skill in the folder (only listed packages + all Atlas extracts).

## Acceptance

- Plan hub lives under Autogenesis Atlas.
- Inventory table of skill→repo and atlas→`<name>-atlas` is in the work hub.
- Implement (later) pushes ours-wins and records each remote URL.
- Skills after split: lean package + `atlas mount` of `<name>-atlas`.

## Pins used

Dedicated Atlas shape. One Atlas root per git repo. APM uncoupled. `p-apm-git-trace` is in-scope for implement (mount after APM copy).

## Migration order (one repo at a time)

Rule: publish a package only after every APM dependency already exists on GitHub at the version we pin. `apm init` on **every** repo, including `*-atlas` (those packages depend on `okf` only; they are stores, not skills).

1. **okf** — no APM skill deps. Format authority. Update existing `sergio-sisternes-epam/okf` (ours wins).
2. **atlas** skill — depends on okf. Update existing `sergio-sisternes-epam/atlas`.
3. **atlas-atlas** — extract `atlas/references/atlas`. Then slim the atlas skill and `atlas mount` this repo.
4. **agent-spec** skill + **agent-spec-atlas** — construct’s `apm.yml` already lists agent-spec. Do this before construct even though it was not in the named wave.
5. **discuss-atlas** then **discuss** skill — `apm init`, depend on atlas + okf. No apm.yml today.
6. **construct-atlas** then **construct** — depends on atlas, okf, agent-spec.
7. **think-atlas** then **think** repo (three skills) — `apm init` per package or one workspace; depend on atlas + okf.
8. **autogenesis-atlas** then **autogenesis** — hub last among the named set so it can record mounts of the others. Depends on atlas + okf.
9. Remaining stores only: `apm-atlas`, `agent-brain-atlas`, `gamma-atlas`, `knowledge-crawl-atlas`, `medium-atlas`, `portfolio-atlas`, `skill-feedback-atlas`, `visual-atlas`. Skills for those stay local until a later wave.

Do not start agent-brain until autogenesis is on GitHub (it depends on autogenesis + atlas + okf).

## Stop

Stops for approval. No `gh` push and no tree split until you accept.
---
