---
domain: tasks
references:
- kind: doc
  role: intent
  target: docs/guide/tasks/completions.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#apply_completion
---

# Completion

One time a task was done, kept in its history.

## Information kept

- **Completed at** — when the work happened
- **Note** — a Markdown note
- **Cost** — what it cost
- **Photo** — an after photo
- **Who** — the Home Assistant person who did it
- **Reading** — the sensor reading at the time, for a usage or threshold task
- **Stock drawn** — how much spare stock the completion took from a part
