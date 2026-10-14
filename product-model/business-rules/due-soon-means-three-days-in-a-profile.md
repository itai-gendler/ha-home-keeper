---
appliesTo:
- type: capability
  id: browse-tasks
- type: capability
  id: create-profile
- type: capability
  id: edit-profile
- type: capability
  id: send-notification
- type: capability
  id: sync-to-do-list
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/card-filter.ts
- kind: code
  role: implementation
  target: custom_components/home_keeper/profiles.py#with_status
- kind: doc
  role: intent
  target: docs/guide/views/profiles.md
- kind: doc
  role: intent
  target: docs/guide/views/dashboard-card.md
---

# Due soon is 3 days in a profile and 7 days on the task list and card

A profile's Overdue and due soon tier, its count sensor, its notifications and its to-do list sync include tasks due in the next 3 days. The Due soon filter of the panel and the dashboard card shows tasks due in the next 7 days.
