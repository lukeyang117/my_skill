---
name: compact-todo
description: "Compress and reorganize repository todo/log agent-memory systems into a dashboard-oriented structure for fast agent onboarding and development: notes/todo.md as a short Start Here dashboard, notes/todo/ branch pages as detailed memory, notes/log/index.md as recent/topic log index, and archives for cold closed history. Use when todo.md, log indexes, or branch pages have grown too large, when agents need a faster start point, or when the memory system created by create-todo-log-systerm needs maintenance compaction."
---

# Compact Todo

## Goal

Make the todo/log memory system fast for agents to use:

- `notes/todo.md` is a dashboard, not a full database.
- `notes/todo/` branch pages are memory.
- `notes/log/` per-test logs are evidence.
- `archive/` files are cold storage for closed history.

Do not optimize for preserving every detail in the root page. Optimize for helping the next agent answer: what is active, what should I read next, what should I avoid redoing, and where is the evidence?

## Shared Layout

Use the same target layout as `$create-todo-log-systerm`:

```text
notes/
├── index.md
├── todo.md
├── todo/
│   ├── README.md
│   ├── T000-notes-workflow.md
│   └── archive/
└── log/
    ├── index.md
    └── archive/
```

Per-test logs stay directly under `notes/log/` until archived.

## Pre-Read

Before changing files, read:

1. repository rules such as `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, or `.codex/RULES.md`
2. `notes/todo.md`
3. `notes/log/index.md`
4. `notes/todo/README.md`
5. branch pages for active/open nodes
6. recent logs linked from active/open nodes

If the repository has stricter todo/log rules, follow them.

## Target Root Dashboard

Keep `notes/todo.md` roughly 60-120 lines. Use these sections:

```md
# Investigation Dashboard

## Start Here
## Status Legend
## Active Fronts
## Root Map
## Open Leaves
## Branch Pages
## Recent Logs
## Maintenance
```

### Start Here

Use this as the agent handoff summary:

```md
## Start Here

- Current focus: T104a
- Read next:
  - [T001-speed-command-alignment.md#t104a...](todo/T001-speed-command-alignment.md#...)
  - [2026-04-25-2132-forward-late-amplitude-seed-tuning.md](log/...)
- Avoid redoing:
  - T401 reachability is closed; use it only as context.
- Current git base: `3518c9f`
```

### Root Map

Only list root themes and their current child/open summary. Do not expand all closed children.

```md
| Root | Status | Stage | Branch | Current | Refs |
| --- | --- | --- | --- | --- | --- |
| T001 | done | viewer -> planner | [T001](todo/T001-speed-command-alignment.md) | active child T104/T104a | feature `38f8f8b`; verified `38f8f8b` |
```

### Open Leaves

List only `todo`, `doing`, `verify`, or `blocked` leaves.

```md
| Leaf | Parent | Status | Priority | Why active | Next read |
| --- | --- | --- | --- | --- | --- |
| T104a | T104 | doing | P0 | forward late tracking collapse | T001 branch + 2132 log |
```

Closed child nodes belong in branch-page `Closed Children Archive`, not in the root dashboard.

## Branch Pages

Use branch pages for durable memory. Recommended sections:

```md
# T100 Problem Theme

## Current State
## Open Children
## Closed Children Archive
## Related Logs
## Git Refs
## Next Step
## Node Details
```

Rules:

- `Current State` must be short, usually 5-10 bullets.
- `Open Children` lists active leaves with next checks.
- `Closed Children Archive` stores one-line closed-node summaries.
- `Node Details` stores long `why-created`, hypotheses, evidence, and decisions.
- Detailed metrics should live in per-test logs; branch pages should link and summarize.

## Log Index

Compact `notes/log/index.md` when it becomes long:

```md
# Test Log Index

## Recent Logs
## Topic Log Index
## Archived Logs
## How To Add A New Entry
```

Rules:

- Keep only the most recent 10-15 log rows in `Recent Logs`.
- Group older important evidence by todo/topic in `Topic Log Index`.
- Move old chronological rows into `notes/log/archive/YYYY-MM.md` or `notes/log/archive/<topic>.md`.
- Do not delete per-test logs unless the user explicitly asks.

## Modes

Choose the lightest mode that solves the problem:

- `daily compact`: update `Start Here`, `Active Fronts`, `Open Leaves`, and recent logs after normal development.
- `root compact`: convert an oversized root todo into the dashboard shape.
- `branch compact`: shorten one branch page by moving closed details into `Closed Children Archive`.
- `log compact`: keep recent logs in `log/index.md`, move old index rows to `log/archive/`.
- `archive compact`: move cold closed root/branch history into archive files while preserving links.

## Workflow

1. Inventory active/open nodes first; they drive the dashboard.
2. Build `Start Here` from the highest-priority active leaf.
3. Build `Root Map` with only root-level themes.
4. Build `Open Leaves` with only open leaves.
5. Move closed children and long details into branch pages.
6. Compact branch pages into `Current State`, `Open Children`, `Closed Children Archive`, and `Node Details`.
7. Compact `log/index.md` if it has too many rows.
8. Update repository rules only when the required read/update workflow changed.
9. Create a notes workflow log if the repository requires logs for memory-system changes.

## Validation

Before claiming completion:

- `notes/todo.md` has `Start Here`, `Active Fronts`, `Root Map`, and `Open Leaves`.
- Root page does not expand every closed child.
- Every open leaf has a branch link and latest/relevant log link.
- Every root theme has a branch page or explicit archive.
- Branch pages preserve closed child summaries and detailed memory.
- `notes/log/index.md` has recent logs and topic/archive links if compacted.
- Relative links resolve outside template code blocks.
- Git refs were preserved in either root `Refs`, branch `Git Refs`, or per-test logs.

Useful checks:

```bash
wc -l notes/todo.md notes/log/index.md notes/todo/*.md
rg -n "## Start Here|## Root Map|## Open Leaves|## Closed Children Archive|## Topic Log Index" notes
rg -n "T[0-9][0-9][0-9][a-z]?" notes/todo.md notes/todo notes/log/index.md
```

## kinematic_footsteps

For `/home/lhy/kinematic_footsteps`, read `references/kinematic-todo-schema.md` before editing its todo/log memory files.
