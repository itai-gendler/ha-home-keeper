---
domain: profiles
availability:
- {place: 'panel::administration'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/options.py#ProfileInUseError
---

# Delete a profile

Remove a profile and its count sensor. A profile a notification uses is not deleted.
