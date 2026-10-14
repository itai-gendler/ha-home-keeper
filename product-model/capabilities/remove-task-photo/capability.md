---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/task_photos.py#remove_photo
---

# Remove a task photo

Delete a photo and its file from a task.
