---
appliesTo:
- type: capability
  id: complete-task
- type: capability
  id: edit-completion
- type: capability
  id: move-completion
- type: capability
  id: delete-completion
- type: capability
  id: undo-completion
references:
- kind: doc
  role: intent
  target: docs/guide/tasks/completions.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#remove_completion
---

# Only the latest completion moves the due date

A completion older than the latest only adds to the history. Editing, moving or deleting an older entry keeps the due date, a snooze and a skip; deleting the latest completion of a fixed task puts back the due date it had before.
