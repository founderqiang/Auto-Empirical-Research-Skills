# Repository Audit - 2026-05-31

This audit was run from the local workspace after fast-forwarding `main` to `origin/main`.

## Snapshot

| Metric | Value |
|---|---:|
| Top-level `skills/` directories | 54 |
| Top-level collections with exact-case `SKILL.md` files | 50 |
| `SKILL.md` files under `skills/` | 969 |
| Total tracked files | 3260 |
| Total workspace size | 116 MB |
| Markdown workflow docs under `docs/` | 10 |
| Existing scheduled sync workflows | 2 |
| Large files over 1 MB | 2 cover images |

## Strengths

- Clear niche: empirical research, econometrics, causal inference, replication, submission, and review response.
- Strong flagship assets: StatsPAI skill, explicit Python/Stata/R empirical-analysis skills, AER-skills, Chinese de-AIGC.
- Bilingual README entry point and workflow-stage docs.
- Existing security scan reports and vendor-sync workflows.
- Rich demo outputs for LaLonde and StatsPAI-style pipelines.

## Issues Found

- README links still pointed to old local paths for StatsPAI and the Python empirical-analysis skill.
- No generated machine-readable catalog despite a large skill inventory.
- No generic repo validation CI for local links, skill frontmatter, or generated catalog freshness.
- No issue templates, pull request template, `SECURITY.md`, `CODE_OF_CONDUCT.md`, or `CITATION.cff`.
- Many vendored `SKILL.md` files exceed the recommended 500-line progressive-disclosure target. This is acceptable for upstream mirrors, but first-party additions should split long details into `references/`.
- A few upstream files are named `skill.md` rather than exact-case `SKILL.md`; these are treated as cleanup warnings because Linux agent runtimes and CI are case-sensitive.

## Changes Made

- Added `scripts/build-catalog.py`, `catalog/skills.json`, and `docs/SKILL_CATALOG.md`.
- Added `scripts/validate-repo.py`, `Makefile`, and `.github/workflows/validate-catalog.yml`.
- Added issue templates for bug reports and skill submissions.
- Added pull request checklist focused on source, license, catalog, validation, and paid-API scope.
- Added project governance files: `SECURITY.md`, `CODE_OF_CONDUCT.md`, `CITATION.cff`.
- Added `docs/QUALITY_GATE.md` and `docs/COMPETITIVE_LANDSCAPE.md`.
- Fixed stale README/README-zh local skill links.

## Recommended Next Steps

1. Add provenance metadata for each top-level collection: upstream URL, license, vendored commit, sync mode, review date.
2. Add a lightweight static search UI over `catalog/skills.json`.
3. Split first-party long `SKILL.md` files into lean spines plus `references/` files.
4. Add a link checker for external URLs on a scheduled workflow, separate from PR CI to avoid network flakes.
5. Add five "golden workflow" demos that show exactly which skills to use for common empirical-research jobs.
