---
availability:
- {place: 'panel::household'}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/todo_list_sync.py#TodoListSync
- kind: doc
  role: intent
  target: docs/guide/views/todo-sync.md
---

# Sync a profile to its to-do list

Keep the tasks a profile selects as items on its to-do list, in another to-do integration, both ways: a checked item completes the task, and a changed due date moves it like a snooze.
