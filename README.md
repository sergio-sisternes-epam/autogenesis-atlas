# autogenesis-atlas

Dedicated Atlas store for the autogenesis skill. This is a **store package**, not a skill — there is no `SKILL.md`.

OKF root is `atlas/` (`atlas/SCHEMA.json`), not the git root. Git root holds only package metadata (`README.md`, `apm.yml`, `.gitignore`, optional `LICENSE`).

Consumers mount this repo, then pass `--root` at the nested `atlas/` directory:

```text
atlas auth login --host github.com
atlas mount github.com/sergio-sisternes-epam/autogenesis-atlas --ref main
atlas compile --root .atlas/github.com/sergio-sisternes-epam/autogenesis-atlas/atlas
atlas search "…" --root .atlas/github.com/sergio-sisternes-epam/autogenesis-atlas/atlas
```

Default clone path: `.atlas/github.com/sergio-sisternes-epam/autogenesis-atlas`  
Compile/query root: `.atlas/github.com/sergio-sisternes-epam/autogenesis-atlas/atlas`

In this repository, compile against `./atlas` (CLI lives in the atlas skill package; it is not vendored here):

```text
atlas compile --root atlas
```

APM dependencies: `sergio-sisternes-epam/okf`, `sergio-sisternes-epam/atlas`.
