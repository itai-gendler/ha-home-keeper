---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#move_completion
---

# Move a completion

Change the date of a recorded completion. Only moving the latest completion moves the due date.
