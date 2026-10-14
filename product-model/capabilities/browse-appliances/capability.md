---
domain: appliances
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/panel-lists.ts
- kind: doc
  role: intent
  target: docs/guide/start/household-users.md
---

# Browse appliances

See the active or archived appliances as a list or as a tree of subdevices, and search them by name, model and serial number. Every signed-in user reads every appliance.
