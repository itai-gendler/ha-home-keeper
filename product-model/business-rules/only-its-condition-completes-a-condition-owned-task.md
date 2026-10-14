---
appliesTo:
- type: entity
  id: completion
  effect: creates
permits:
- unattended: true
- actors:
  - household-member
  - admin
  - automation
  - companion
  when:
  - entity: task
    fact: Completed by its condition
    is: 'No'
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/store.py#_reject_completion_blocked
- kind: doc
  role: intent
  target: docs/guide/tasks/triggered-tasks.md
---

# Only the recovery of its condition completes a task it owns

A synced problem-sensor task, and a declarative companion's task that clears itself, is completed only by Home Keeper when the condition recovers. Every surface refuses Done by hand and says the condition must recover.

## Rationale

A completion by hand while the condition is still true records work that was not done.
