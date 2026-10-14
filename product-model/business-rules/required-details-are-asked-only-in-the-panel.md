---
appliesTo:
- type: capability
  id: complete-task
- type: capability
  id: edit-task
references:
- kind: doc
  role: intent
  target: docs/guide/tasks/completions.md
---

# The completion dialog and required details apply only in the panel

A task that asks for or requires details opens the completion dialog in the panel, and Require details keeps Done off until the required fields are filled. Every other surface completes at once with what it passes; the dashboard card sends a task that requires details to its page in the panel.
