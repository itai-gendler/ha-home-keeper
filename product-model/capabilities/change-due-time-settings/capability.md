---
availability:
- {place: 'panel::administration'}
- {place: services}
references:
- kind: doc
  role: intent
  target: docs/guide/views/settings.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#snap_to_due_time
---

# Change the due time settings

Choose when a task that repeats after each completion is due: at the time of its completion, or at a set time of day.
