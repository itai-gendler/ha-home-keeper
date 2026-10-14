---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: dashboard-card}
- {place: native-entities}
- {place: services}
references:
- kind: doc
  role: intent
  target: docs/guide/start/panel.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/panel-lists.ts
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/card-filter.ts
- kind: code
  role: implementation
  target: custom_components/home_keeper/todo.py
- kind: code
  role: implementation
  target: custom_components/home_keeper/calendar.py
---

# Browse tasks

See the tasks with their status — overdue, due today, due soon, later, monitored, counted, shopping, disabled and completed — and narrow them by scope, search, profile and grouping. The dashboard card shows the tasks its own filter selects, and the native to-do list and calendar show the tasks that are due.
