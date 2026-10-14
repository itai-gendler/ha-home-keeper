---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/store.py#HomeKeeperStore
- kind: code
  role: implementation
  target: custom_components/home_keeper/models.py#deletion_blocked
- kind: doc
  role: intent
  target: docs/guide/tasks/one-off-tasks.md
---

# Delete a task

Remove a task with its history and photos. Its completions stay in its appliance's history. Home Keeper also deletes completed one-off tasks once the retention period has passed.
