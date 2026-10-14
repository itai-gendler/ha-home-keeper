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
  target: custom_components/home_keeper/models.py#merge_update
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/panel-task-form.ts
---

# Edit a task

Change a task's name, notes, schedule, placement, labels, completion options, tag, snooze length, linked consumable and card links, from the edit form beside the task's page, the inline note editor, or the update task action.
