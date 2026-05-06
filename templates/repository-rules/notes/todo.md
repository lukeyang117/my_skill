# Investigation Dashboard

This page is the fast-start dashboard for agent work. It is not a full database. Detailed memory lives in [todo/](todo/); evidence lives in [log/](log/).

## Start Here

- Current focus: none yet
- Read next:
  - [T000 notes workflow](todo/T000-notes-workflow.md)
  - [bootstrap log](log/BOOTSTRAP_TIME-notes-workflow-bootstrap.md)
- Avoid redoing:
  - Do not recreate the memory system; update it incrementally.
- Current git base: `CURRENT_GIT_BASE`

## Status Legend

- `todo`: not started
- `doing`: under investigation
- `blocked`: waiting on a condition
- `verify`: changed or hypothesized, awaiting verification
- `done`: completed and closed
- `drop`: abandoned direction

## Active Fronts

| Leaf | Why Active Or Next | Suggested Action |
| --- | --- | --- |
| none | No active project issue yet. | Add a real root node when work begins. |

## Root Map

| Root | Status | Stage | Branch | Current | Refs |
| --- | --- | --- | --- | --- | --- |
| T000 | done | notes workflow | [T000](todo/T000-notes-workflow.md) | memory system bootstrapped | feature `CURRENT_GIT_BASE`; verified `CURRENT_GIT_BASE` |

## Open Leaves

| Leaf | Parent | Status | Priority | Why Active | Next Read |
| --- | --- | --- | --- | --- | --- |
| none | none | done | P0 | No open issue yet. | Add a real leaf when work begins. |

## Branch Pages

- [todo/README.md](todo/README.md)
- [T000-notes-workflow.md](todo/T000-notes-workflow.md)

## Recent Logs

| Time | Topic | Result | Todo | File |
| --- | --- | --- | --- | --- |
| BOOTSTRAP_DATE_TIME | notes workflow bootstrap | pass | [T000](todo/T000-notes-workflow.md) | [BOOTSTRAP_TIME-notes-workflow-bootstrap.md](log/BOOTSTRAP_TIME-notes-workflow-bootstrap.md) |

## Maintenance

- Keep this page short: dashboard only.
- Put detailed background and conclusions in branch pages.
- Put metrics and command output in per-test logs.
- Use `$compact-todo` when this page, branch pages, or log index grow too large.
