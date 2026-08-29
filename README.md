---
type: document
title: "autogenesis-atlas"
created: 2026-08-30
description: "Dedicated Atlas store for the autogenesis skill. Git root is the OKF root."
origin: internal
sensitivity: public
---

# autogenesis-atlas

Dedicated Atlas store for the autogenesis skill. This is a **store package**, not a skill — there is no `SKILL.md`.

OKF root is the **git clone root** (`SCHEMA.json`), not a nested `atlas/` folder. Nested `atlas/atlas` on mount was the bug this layout fixes.

Consumers mount this repo, then pass `--root` at the clone root:

```text
atlas auth login --host github.com
atlas mount github.com/sergio-sisternes-epam/autogenesis-atlas --ref main
atlas compile --root .atlas/github.com/sergio-sisternes-epam/autogenesis-atlas
atlas search "…" --root .atlas/github.com/sergio-sisternes-epam/autogenesis-atlas
```

Default clone path and compile/query root: `.atlas/github.com/sergio-sisternes-epam/autogenesis-atlas`

In this repository, compile against the clone root (CLI lives in the atlas skill package; it is not vendored here):

```text
atlas compile --root .
```

Git root holds OKF pages (`SCHEMA.json`, `index.md`, `log.md`, spaces) plus package metadata (`README.md`, `apm.yml`, `.gitignore`, optional `LICENSE`).

APM dependencies: `sergio-sisternes-epam/okf`, `sergio-sisternes-epam/atlas`.
