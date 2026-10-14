---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: dashboard-card}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/panel-detail.ts
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/panel-history.ts
- kind: doc
  role: intent
  target: docs/guide/views/dashboard-card.md
---

# View a task

Open one task's page to read its schedule, notes, photos and history, including the progress of a usage task and the usage between completions. The dashboard card opens a task's note and cover photo.
