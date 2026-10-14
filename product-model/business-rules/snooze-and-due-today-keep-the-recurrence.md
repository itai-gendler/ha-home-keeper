---
appliesTo:
- type: capability
  id: snooze-task
- type: capability
  id: make-task-due-today
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#snooze_from
---

# Snooze and Due today move only the due date

Neither records a completion or changes the recurrence; a snooze never moves a task earlier than its due date, and a task with no due date can be neither snoozed nor made due today.
