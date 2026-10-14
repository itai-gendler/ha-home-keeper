---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: dashboard-card}
- {place: services}
references:
- kind: doc
  role: intent
  target: docs/guide/tasks/snooze-and-skip.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/store.py#HomeKeeperStore
---

# Make a task due today

Move a task's due date to today without a completion and without changing its recurrence. Offered on a task that is not yet due, while Due today is on in the settings.
