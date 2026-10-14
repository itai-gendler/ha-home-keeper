---
appliesTo:
- type: entity
  id: task
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/recurrence.py#compute_next_due
- kind: doc
  role: intent
  target: docs/guide/start/concepts.md
---

# Each schedule kind sets the due date its own way

A task that repeats after each completion is due one interval after its latest completion, and a missed one stays overdue. A fixed schedule is due at its next occurrence, keeping its time of day across clock changes. A one-off task is due once. Triggered and sensor-based tasks have no due date until their condition holds, and are then due now. An active season moves a due date outside its windows to the start of the next window.
