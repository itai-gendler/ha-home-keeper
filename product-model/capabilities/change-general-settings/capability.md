---
availability:
- {place: 'panel::administration'}
- {place: services}
references:
- kind: doc
  role: intent
  target: docs/guide/tasks/one-off-tasks.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/options.py
---

# Change the general settings

Set how many days a completed one-off task is kept, up to 3650; 0 keeps it forever. A lower value applies at the next periodic check.
