---
domain: profiles
availability:
- {place: 'panel::administration'}
- {place: services}
references:
- kind: doc
  role: intent
  target: docs/guide/views/profiles.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/profiles.py#normalize_profile
---

# Create a profile

Save a filter of tasks with a status tier and include and exclude filters, for the task list, the card, notifications and to-do list syncs. Each profile also gets a count sensor.
