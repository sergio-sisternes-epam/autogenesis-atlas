---
type: plan
title: "Design plan: path atlas-migrate (extend atlas migrate with Autogenesis discipline)"
created: 2026-08-23
work_id: autogenesis-path-atlas-migrate-v1
status: done
change_class: new-surface
subject: autogenesis
description: "Formal design from discussion pins. Stops for approval — do not implement until approved."
relates_to:
  - path: autogenesis/work/autogenesis-path-atlas-migrate-v1.md
    kind: implements
  - path: autogenesis/decisions/plan-home-is-subject-atlas.md
    kind: related
  - path: autogenesis/decisions/memory-substrate-is-atlas.md
    kind: related
  - path: autogenesis/plans/atlas-migrate-cli-improve-v1.md
    kind: related
---

## Intent + scope

Add Autogenesis path **`atlas-migrate`**: operator discipline for migrating a subject’s legacy okf-wiki (or override path) into the subject Atlas under **`autogenesis/`**, using **atlas CLI migrate/promote/compile** as the mechanical core.

### In scope
- New file `references/paths/atlas-migrate.md`
- SKILL.md capabilities registry row
- Procedure encoding discussion pins + self-migration lessons
- Work/experience records on Exit in subject Atlas Autogenesis space
- After green compile: rewrite subject discipline toward Atlas-only memory + plan home

### Non-goals
- Replacing or forking atlas CLI migrate
- Requiring CLI improvements (dry-run, batch, --carry-body) before path ships
- Auto claim synthesis without agent judgment
- BM25 / full product live-migration engine (`atlas-bm25-and-live-migration-v1`)

## Pins (from discussion — authoritative)

1. **Source:** autodiscover okf-wiki; default `<subject>/references/wiki/`; user override allowed.
2. **No Atlas:** auto-initiate minimal subject Atlas including full `autogenesis/` space (SCHEMA `initiate_includes`); stop only on bootstrap failure.
3. **Completeness:** every staged content file → claim-bearing page under `autogenesis/` before Exit (no bulk defer of raw experiences).
4. **Discipline:** after compile green, also rewrite subject SKILL/paths for Atlas-only memory and `autogenesis/plans/<work_id>.md` plan home.
5. **CLI:** ship against today’s atlas migrate/promote/compile.
6. **Name:** path_id `atlas-migrate`.

## Genesis Artifacts

### Intent + scope + non-goals
See above.

### Mermaid (sequence)

```mermaid
sequenceDiagram
  participant User
  participant AG as autogenesis atlas-migrate
  participant Atlas as atlas CLI
  participant Store as subject Atlas

  User->>AG: path atlas-migrate (subject, optional source)
  AG->>AG: resolve subject; default source references/wiki
  alt no Atlas
    AG->>Store: auto-initiate SCHEMA + autogenesis/ tree
  end
  AG->>Atlas: migrate source --root subject_atlas
  Atlas->>Store: staging/ filled
  loop each staged content file
    AG->>Atlas: promote (or direct claim write)
    AG->>Store: complete type + body + relates_to under autogenesis/
  end
  AG->>Atlas: compile --root subject_atlas
  Atlas-->>AG: green (staging empty)
  AG->>Store: rewrite subject discipline Atlas-only
  AG->>Store: Exit experience + work hub update
```

### Interface sketch

**Activation**
```text
mode: run
subject: <skill>
path: atlas-migrate
path_module: references/paths/atlas-migrate.md
intent: migrate <subject> process memory to Atlas Autogenesis space
```

**Optional user inputs**
- `source:` override path (default `<subject>/references/wiki/`)
- subject from Enter card

**CLI (unchanged)**
```text
atlas migrate <source> --root <subject>/references/atlas
atlas promote <staging-file> --to autogenesis/<type-folder>/<name>.md --type …
atlas compile --root <subject>/references/atlas
```

**Claim routing**
| Source kind | Target |
|-------------|--------|
| knowledge / durable claims | `autogenesis/decisions/` type decision |
| raw experiences | `autogenesis/experiences/` type experience |
| formal design packets (if detected) | `autogenesis/plans/<work_id>.md` type plan |
| work hubs | `autogenesis/work/<work_id>.md` |

**Path receipt fields**
`subject`, `path: atlas-migrate`, `atlas_root`, `source`, `promoted_count`, `compile: yes`, `discipline_rewrite: yes|deferred-reason`, `Enter|Change|Exit`

### Cost note
Dominant cost is agent claim conversion of large raw/ trees (O(n) pages). Acceptable per pin 3; no new long-running services.

## Acceptance

1. Path module exists and is listed in SKILL capabilities registry.
2. Default source is subject `references/wiki/`; override honored when provided.
3. Missing Atlas → auto-initiate with `autogenesis/` tree; no user gate unless failure.
4. Exit refuses success if staging non-empty or compile red.
5. Exit refuses success if any content file left only in staging without a claim-bearing target under `autogenesis/`.
6. After green compile, subject SKILL (and relevant path text) updated for Atlas memory + plan home—or explicit incomplete if rewrite blocked.
7. Multi-harness substrate contract used when invoking **atlas** (and **okf** for format-only).
8. No implement of this path until this plan is explicitly approved.

## Residual risks

- Full claim conversion of huge wikis is slow/token-heavy — accepted by pin 3.
- Discipline rewrite heuristics may miss subject-specific wording — mitigate with checklist + compile/search of remaining “okf-wiki” memory authority strings.
- Promote scaffold-only still requires agent body completion — path must document re-read source before clearing staging.

## Challenge (automated×1; confidence: limited)

| Counter | Disposition |
|---------|-------------|
| Auto-initiate without consent is dangerous | **Rejected for this path** — user pinned auto-initiate; document in path Enter; failure still stops |
| Bulk defer should remain | **Rejected** — pin 3 requires full claim conversion |
| Path should wait for CLI batch helpers | **Rejected** — pin 5 ships on current CLI |
| Discipline rewrite belongs in a separate path | **Rejected** — pin 4 folds it into Exit of atlas-migrate |
| Naming collision with atlas CLI “migrate” | **Accepted residual** — path_id is `atlas-migrate`; docs stress CLI vs path |

C1–C5: non-trivial counters considered; high-severity consent risk pinned as accepted residual with failure-stop; pins visible; scope intact; **no implementation in this design Run**.

## Stop for approval

**Do not implement** until explicit user approval of this plan (`approve`, `implement the plan`, or equivalent).
