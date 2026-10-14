---
appliesTo:
- type: capability
  id: delete-task
- type: capability
  id: view-appliance
references:
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/store.py#HomeKeeperStore
---

# A deleted task's completions stay on its appliance

The maintenance history of an appliance keeps the completions of tasks deleted while they were attached to it; the photos are not kept.
