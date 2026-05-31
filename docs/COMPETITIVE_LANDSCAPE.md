# Competitive Landscape

Scan date: 2026-05-31.

This note records the public repositories and directories used to sharpen AERS. The point is not to imitate general-purpose skill indexes, but to make AERS the best domain-specific index for empirical research.

## References Checked

| Project | What it does well | What AERS should adopt |
|---|---|---|
| [anthropics/skills](https://github.com/anthropics/skills) | Official reference implementation. It makes the core contract explicit: each skill is a self-contained folder with a `SKILL.md` file, required `name` and `description` frontmatter, optional scripts/references/assets, and examples/templates. | Keep AERS skill metadata machine-checkable; make the catalog deterministic; push first-party skills toward progressive disclosure. |
| [awesomeskills.dev](https://www.awesomeskills.dev/) | Search-first marketplace positioning: indexed skills, collections, resources, submit flow, and multilingual discovery. | Provide a generated `catalog/skills.json` and browsable `docs/SKILL_CATALOG.md` so AERS can power a future search UI. |
| [itgoyo/awesome-claude-code-skills](https://github.com/itgoyo/awesome-claude-code-skills) | Star-sorted awesome-list mechanics, concise contribution criteria, one-line descriptions, and visible "last updated" provenance. | Keep entries concise; require source, license, category, and one-line functional description in issues/PRs. |
| [Agent Skills: A Data-Driven Analysis](https://arxiv.org/abs/2602.08004) | Shows that public skills are rapidly proliferating, often redundant, and can pose safety risks when they enable state-changing or system-level actions. | Differentiate by domain depth, provenance, security review, and empirical-research workflow organization rather than raw count alone. |

## Positioning

AERS should be framed as:

- The empirical-research specialist, not a general agent-skill marketplace.
- A bridge between skill discovery and runnable research workflows.
- A security-audited, license-aware, reproducibility-focused catalog.
- A practical on-ramp to StatsPAI, AER-skills, and other high-value causal-inference workflows.

## Gaps Fixed In This Pass

- Added deterministic generated catalog outputs.
- Added repository validation and CI.
- Added contribution, issue, and pull request templates that collect source/license/category data.
- Added security, citation, and conduct files expected by serious open-source users.

## Next Competitive Moves

- Add a small static search page over `catalog/skills.json`.
- Add per-upstream provenance metadata: source URL, license, vendored commit, sync mode, security review date.
- Add a "top workflows" page with 5 copy-paste prompts: DID, IV, replication package, AER submission, Chinese de-AIGC.
- Add install snippets for Claude Code, Codex, and manual local copying where each runtime supports it.
