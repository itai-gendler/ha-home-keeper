---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: dashboard-card}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/task_photos.py#append_photo
- kind: doc
  role: intent
  target: docs/guide/tasks/task-photos.md
---

# Add a task photo

Add a photo to a task, up to 6, from the task's page or the dashboard card. The first photo is the cover.
