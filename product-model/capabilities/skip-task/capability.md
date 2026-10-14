---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: dashboard-card}
- {place: mobile-notifications}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#skip_occurrence
- kind: doc
  role: intent
  target: docs/guide/tasks/snooze-and-skip.md
---

# Skip a task

Pass over one occurrence: a repeating task starts a new interval now, a fixed task moves to its next date, a usage task starts from the current reading, and a condition task returns to monitored. The skip is recorded apart from completions.
