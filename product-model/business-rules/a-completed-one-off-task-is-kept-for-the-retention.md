---
appliesTo:
- type: capability
  id: delete-task
- type: capability
  id: change-general-settings
references:
- kind: doc
  role: intent
  target: docs/guide/tasks/one-off-tasks.md
---

# A completed one-off task is kept for the retention period

One-off retention 0 keeps a completed one-off task forever; a higher value, up to 3650 days, deletes it that many days after its completion.
