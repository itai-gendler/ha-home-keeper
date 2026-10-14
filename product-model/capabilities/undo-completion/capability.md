---
domain: tasks
availability:
- {place: 'panel::household'}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/panel.ts
- kind: doc
  role: intent
  target: docs/guide/tasks/completions.md
---

# Undo a completion

Take back a one-tap Done from the message that follows it. The task gets its previous due date again.
