---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#update_completion
- kind: doc
  role: intent
  target: docs/guide/tasks/completions.md
---

# Edit a completion

Change the recorded note, cost, photo, person or reading of a completion without moving the schedule. Editing the reading of the latest completion moves the meter anchor.
