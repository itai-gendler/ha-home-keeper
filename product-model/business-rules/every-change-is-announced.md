---
appliesTo:
- type: capability
  id: create-task
- type: capability
  id: edit-task
- type: capability
  id: complete-task
- type: capability
  id: delete-task
- type: capability
  id: skip-task
- type: capability
  id: snooze-task
- type: capability
  id: arm-task
- type: capability
  id: adjust-part-stock
references:
- kind: doc
  role: intent
  target: docs/guide/automation/events.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/events.py
---

# Every change to a task, appliance or part stock fires a Home Keeper event

Creating, updating, completing, skipping, snoozing, arming and deleting a task, each appliance change and each stock crossing fire a home_keeper event that automations and companions can use; an update with no real change fires nothing.
