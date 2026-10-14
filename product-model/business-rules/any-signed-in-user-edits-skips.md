---
appliesTo:
- type: entity
  id: skip
  effect: changes
permits:
- actors:
  - household-member
  - admin
  - automation
  - companion
- unattended: true
references:
- kind: doc
  role: intent
  target: docs/SECURITY.md
- kind: doc
  role: intent
  target: docs/guide/start/household-users.md
---

# Any signed-in user edits skips

A skip is household data that follows its task: every signed-in user, admin or not, edits skips, and so do automations and companions. Home Keeper itself also does when a schedule, a sensor or a sync acts.

## Rationale

A user who can create a task can also edit it, delete it, complete it and add its photos.
