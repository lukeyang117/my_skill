# My Skill

Reusable Codex skills and repository-rule templates for a notes-based agent memory workflow.

## Included Skills

- `compact-todo`: compacts an existing `notes/todo.md` and `notes/log/index.md` system into a dashboard plus branch-memory layout.
- `create-todo-log-systerm`: bootstraps the same todo/log memory system in a repository that does not have it yet.
- `inspire`: gates implementation behind an explicit `/inspire` discussion flow for requirement analysis, design generation, todo breakdown, and delegated execution.

The `create-todo-log-systerm` name keeps the original installed skill name for compatibility.

## Install From GitHub

Install the skills into `$CODEX_HOME/skills`:

```bash
python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo lukeyang117/my_skill \
  --path skills/compact-todo skills/create-todo-log-systerm skills/inspire
```

Restart Codex after installing new skills.

You can also ask Codex directly:

```text
Use $skill-installer to install skills/compact-todo, skills/create-todo-log-systerm, and skills/inspire from https://github.com/lukeyang117/my_skill.
```

## Manual Install

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -a skills/compact-todo "${CODEX_HOME:-$HOME/.codex}/skills/"
cp -a skills/create-todo-log-systerm "${CODEX_HOME:-$HOME/.codex}/skills/"
cp -a skills/inspire "${CODEX_HOME:-$HOME/.codex}/skills/"
```

## Repository Rules Template

`templates/repository-rules/` contains a portable version of the hard repository workflow:

- `AGENTS.md`
- `.codex/RULES.md`
- `notes/index.md`
- `notes/todo.md`
- `notes/todo/README.md`
- `notes/todo/T000-notes-workflow.md`
- `notes/log/index.md`
- `notes/log/BOOTSTRAP_TIME-notes-workflow-bootstrap.md`

Usually you should use `$create-todo-log-systerm` instead of copying these by hand, because the skill replaces project-specific placeholders and writes a timestamped bootstrap log.

## Typical Use

Bootstrap a new repository:

```text
Use $create-todo-log-systerm to add the notes/todo/log memory system to this project.
```

Maintain an existing repository:

```text
Use $compact-todo to compact this repository's todo/log memory dashboard.
```

Analyze before implementation:

```text
Use $inspire to analyze this requirement, bug, image, or reference mapping before implementation.
```

## Layout

```text
skills/
  compact-todo/
  create-todo-log-systerm/
  inspire/
templates/
  repository-rules/
```
