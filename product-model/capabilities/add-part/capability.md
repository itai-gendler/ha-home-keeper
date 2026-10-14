---
domain: appliances
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/reconcile.py#reconcile_part_tasks
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
---

# Add a part

Add a consumable or a wear item to an appliance. A wear item with a replacement interval makes a maintenance task named by its action; a wear item that counts uses makes a use task and a replacement task.
