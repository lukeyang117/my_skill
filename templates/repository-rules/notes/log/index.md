# Test Log Index

This page indexes verification evidence. Keep it short enough to scan.

## Recent Logs

| Time | Topic | Stage | Result | Key Metrics | Todo | File |
| --- | --- | --- | --- | --- | --- | --- |
| BOOTSTRAP_DATE_TIME | notes workflow bootstrap | notes workflow | pass | dashboard memory system created | [T000](../todo.md#root-map) | [BOOTSTRAP_TIME-notes-workflow-bootstrap.md](BOOTSTRAP_TIME-notes-workflow-bootstrap.md) |

## Topic Log Index

- T000 notes workflow:
  - [BOOTSTRAP_TIME-notes-workflow-bootstrap.md](BOOTSTRAP_TIME-notes-workflow-bootstrap.md)

## Archived Logs

- none yet

## How To Add A New Entry

1. Create one log file under `notes/log/`.
2. Add a row to `Recent Logs`.
3. Add or update the topic group in `Topic Log Index`.
4. Update `notes/todo.md` and relevant branch pages.
5. If `Recent Logs` grows too long, move older rows to `notes/log/archive/`.

## Copyable Row Template

```text
| YYYY-MM-DD HH:MM | topic | stage | pass/fail/partial | metric summary | [T001](../todo.md#open-leaves) | [YYYY-MM-DD-HHMM-topic.md](YYYY-MM-DD-HHMM-topic.md) |
```
