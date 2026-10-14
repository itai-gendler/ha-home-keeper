---
domain: tasks
references:
- kind: doc
  role: intent
  target: docs/guide/tasks/snooze-and-skip.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#record_skip
---

# Skip

One occurrence of a task that was passed over on purpose. A skip is never a completion.

## Information kept

- **Skipped at** — when
- **Note** — why
- **Who** — the person who decided
