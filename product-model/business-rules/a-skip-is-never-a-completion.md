---
appliesTo:
- type: capability
  id: skip-task
- type: capability
  id: edit-skip
- type: capability
  id: move-skip
- type: capability
  id: delete-skip
references:
- kind: doc
  role: intent
  target: docs/guide/tasks/snooze-and-skip.md
---

# A skip is never a completion

Skips are kept apart from completions; the completion tally, the average interval and the last completed date never count them.
