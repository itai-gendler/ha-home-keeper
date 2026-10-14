---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#remove_completion
- kind: doc
  role: intent
  target: docs/guide/tasks/completions.md
---

# Delete a completion

Remove a recorded completion from a task's history. Deleting the latest completion of a fixed task puts back the due date it had before; deleting an older one keeps the due date.
