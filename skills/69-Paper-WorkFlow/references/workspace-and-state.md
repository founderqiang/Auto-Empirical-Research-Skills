# Workspace and State Contract

This reference defines the files that the paper-workflow orchestrator creates before it calls any downstream empirical-paper skills.

## Workspace Layout

Create a new workspace under the user-selected project directory:

```text
paper_workspace/<research-short-name>_<YYYYMMDD-HHMM>/
├── 00_meta/
├── 01_proposal/
│   └── candidates/
├── 02_data/
│   └── raw/
├── 03_analysis/
│   ├── results/
│   └── robustness/
├── 04_results/
├── 05_draft/
├── 06_polish/
├── 07_dehumanize/
├── 08_review/
├── 09_submission/
├── logs/
└── backups/
```

Use `assets/init_workspace.sh <workspace-dir>` to create this layout. The script refuses to overwrite an existing path; if a collision occurs, choose a new timestamped directory.

## State File

Copy `assets/workflow_state.template.json` to `00_meta/workflow_state.json` during Stage 0 setup, then fill in:

- `project.short_name`
- `project.created_at_beijing`
- `project.entry_stage`
- `project.mode`
- `project.target_journal`
- `project.language`

Each stage status must be one of `pending`, `in_progress`, `done`, or `skipped`. Set a stage to `in_progress` before work starts and to `done` only after the stage deliverables and review gate are complete.

## Artifact Tracking

Use `artifacts` as a map from stable artifact names to workspace-relative paths, for example:

```json
{
  "proposal": "01_proposal/proposal.md",
  "clean_data": "02_data/clean.parquet",
  "main_results": "03_analysis/results/main_results.json"
}
```

Use `decisions` for human or automated workflow decisions that affect later stages, such as target-journal choice, identification-strategy changes, or fallback paths after failed robustness checks.

## Backup Discipline

At the end of each stage, copy the stage's key outputs into `backups/after_stage<N>/`. The backup is a recovery point for interrupted runs and for conflicts introduced by external editors such as Overleaf or sync clients.
