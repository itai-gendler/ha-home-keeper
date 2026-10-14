---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: dashboard-card}
- {place: native-entities}
- {place: mobile-notifications}
- {place: nfc-tags}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/store.py#_reject_scan_required
- kind: code
  role: implementation
  target: custom_components/home_keeper/store.py#_reject_completion_blocked
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#apply_completion
- kind: code
  role: implementation
  target: custom_components/home_keeper/tag_listener.py
- kind: code
  role: implementation
  target: custom_components/home_keeper/button.py
- kind: doc
  role: intent
  target: docs/guide/tasks/completions.md
- kind: doc
  role: intent
  target: docs/guide/tasks/nfc-tags.md
---

# Complete a task

Mark a task done. The completion is kept in the task's history and the task moves to its next due date: one interval after the completion for a repeating task, the next occurrence of a fixed schedule, none for a one-off. A completion re-anchors a meter, draws spare stock from a linked part, restocks a part from its buy task, counts a use, or returns a condition task to monitored. Every surface completes tasks; Home Keeper itself completes a task when its condition recovers.
