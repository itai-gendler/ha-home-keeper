---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#update_skip
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/panel-history.ts
---

# Delete a skip

Remove a recorded skip; deleting the latest skip undoes it.
