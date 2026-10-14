---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/task_photos.py#make_cover
---

# Make a photo the cover

Choose which photo is a task's cover, shown on its row, its page and the completion dialog.
