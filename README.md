# AI301 fetch smoke test

Throwaway fixture for checking what the AI grading pipeline actually fetches.
**Safe to delete.** Nothing here is course content.

Every file states its own intended path on its first line as `MARKER: <path>`.
Point the grader at a URL below, then compare the `### <path>` headings it
reports against those markers.

## What to submit

| Submit this URL | Expect |
|---|---|
| `.../tree/standardized/maya-chen` | Paths rooted at `maya-chen/`, e.g. `tools/plan-check/README.md`. Derek's files absent. |
| `.../tree/standardized/derek-okafor` | Same shape, derek's markers only. |
| `.../tree/standardized` | Both personas, paths prefixed `maya-chen/...` and `derek-okafor/...`. |
| `.../tree/calib/round-1/maya-chen` | Multi-segment branch name. Should resolve branch `calib/round-1`, subfolder `maya-chen`. |
| `.../blob/standardized/maya-chen/README.md` | **Not** re-rooted. Expect default branch, repo root, everything pulled in. |

## What each file is probing

- `tools/plan-check/README.md` — path-literal criterion target
- `beat-1-sandbox/unit-3/plan.md` — the cross-unit read
- `phase-file-hazards.md` — fenced block, `###` heading, and a literal close tag
- `data/labels.json` — 30-line truncation on data files
- `notes.sh`, `config.toml`, `Makefile` — extension whitelist (expect excluded)
- `deep/a/b/c/d/buried.md` — recursion depth
