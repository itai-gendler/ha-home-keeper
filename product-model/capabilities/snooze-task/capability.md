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
  target: custom_components/home_keeper/recurrence.py#snooze_from
- kind: doc
  role: intent
  target: docs/guide/tasks/snooze-and-skip.md
---

# Snooze a task

Move a due date later without changing the recurrence, by a duration or to a date. A duration starts at the due date, or now when the task is already due. Snooze is offered while Snooze is on in the settings; the action works either way.
