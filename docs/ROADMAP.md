# Roadmap

This roadmap is scoped to making AERS a high-quality, high-trust GitHub project rather than just a large link collection.

## Now

- Keep `catalog/skills.json` and `docs/SKILL_CATALOG.md` current.
- Require `make validate` for all pull requests.
- Keep README links and docs category links green.
- Preserve the no-paid/proprietary-core scope rule for new listings.

## Next

- Add provenance metadata for each vendored collection.
- Build a static search page backed by `catalog/skills.json`.
- Add "golden workflow" examples for common empirical research tasks:
  - Full DID pipeline.
  - IV with weak-instrument diagnostics.
  - AER submission preflight.
  - Replication package audit.
  - Chinese academic de-AIGC pass.
- Add scheduled external-link checking outside PR CI.

## Later

- Package first-party AERS skills as installable bundles for agent runtimes that support plugins/marketplaces.
- Add per-skill eval prompts for flagship first-party skills.
- Maintain a public benchmark of empirical-research agent workflows: correctness, reproducibility, citation hygiene, and runtime safety.
