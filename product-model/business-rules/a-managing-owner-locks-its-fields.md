---
appliesTo:
- type: capability
  id: edit-task
- type: capability
  id: edit-part
- type: capability
  id: delete-task
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/reconcile.py#is_part_owned_name_update
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
---

# The fields a managing owner locks cannot be edited

A companion or a declarative companion names the fields of its task that it owns, and the task form does not offer them. A task an appliance part makes takes its name and tag from the part; such a task is changed and deleted through the part.
