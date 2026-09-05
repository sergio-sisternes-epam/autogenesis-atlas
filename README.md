---
type: document
title: "autogenesis-atlas"
created: 2026-08-30
description: "Dedicated Atlas store for the autogenesis skill. Git root is the OKF root."
origin: internal
sensitivity: public
---

# autogenesis-atlas

Dedicated Atlas store for the autogenesis skill.

This repository is a **mutable knowledge store**, not an APM package or skill.
It therefore has no `apm.yml`, APM lockfile, package version, or independent
release lifecycle. Git root is the OKF root (`SCHEMA.json`), not a nested
`atlas/` folder.

## Mount

Consumers mount an exact store commit, then use the resolved clone root for
compile and query operations. Do not use `main` as a durable consumer pointer.

```text
atlas auth login --host github.com
atlas mount github.com/sergio-sisternes-epam/autogenesis-atlas \
  --ref <40-character-store-commit>
atlas resolve github.com/sergio-sisternes-epam/autogenesis-atlas
```

The default mount is
`.atlas/github.com/sergio-sisternes-epam/autogenesis-atlas`. Pass the path
printed by `atlas resolve` to `atlas compile --root` or
`atlas search --root`.

## Validate

Atlas is released separately. Validate this store with
`sergio-sisternes-epam/atlas#v0.8.15`, whose tag resolves to commit
`4d4796ba66f3de284fbf1df33f5d24a7f5da1980`:

```text
python3 <atlas-v0.8.15>/scripts/atlas.py compile --root . --json
```

The unfocused compile validates the root schema, OKF frontmatter and links,
KVA-state constraints, indexes, and empty staging. Exit `0` passes, exit `1`
passes with warnings retained for review, and exit `2` fails.

GitHub Actions validates the exact pull-request head, pushed commit, or current
`main` commit selected by a manual run. It verifies the Atlas release tag
against the pinned commit before installation, prints the compile JSON, and
uploads the JSON plus candidate metadata as evidence.

## CI credential

Because `sergio-sisternes-epam/atlas` is private, configure the repository
Actions secret `ATLAS_CLI_TOKEN` with read-only metadata and contents access to
that repository. The workflow uses it only to acquire the pinned Atlas release.
It does not pass the secret to fork pull requests; those runs fail closed and
must be reproduced from a trusted branch before merge.
