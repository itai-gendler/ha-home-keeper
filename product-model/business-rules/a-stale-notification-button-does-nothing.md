---
appliesTo:
- type: capability
  id: complete-task
- type: capability
  id: snooze-task
- type: capability
  id: skip-task
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/notifications.py#is_current_action
---

# A button on a notification that is no longer current does nothing

When the task changed after the notification was sent, Mark done, Snooze and Skip on it leave the task as it is.
