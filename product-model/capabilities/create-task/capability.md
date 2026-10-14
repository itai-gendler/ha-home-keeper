---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: dashboard-card}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/models.py#build_task
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/panel-task-form.ts
- kind: doc
  role: intent
  target: docs/guide/start/concepts.md
- kind: doc
  role: intent
  target: docs/guide/tasks/one-off-tasks.md
- kind: doc
  role: intent
  target: docs/guide/tasks/sensor-tasks.md
---

# Create a task

Add a task with its schedule: repeating after each completion, on a fixed schedule, just once, or based on a sensor. Duplicate opens the same form with a copy of another task. The dashboard card adds tasks, and automations and companions add them through the services, including condition-driven tasks a companion owns.
