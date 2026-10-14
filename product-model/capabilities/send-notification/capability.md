---
domain: notifications
availability:
- {place: mobile-notifications}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/notifier.py#async_run_notify
- kind: code
  role: implementation
  target: custom_components/home_keeper/notifications.py#build_notification
---

# Send a notification

Send the due tasks of a profile to the phones: one task at a time for a walk, one summary for a digest. A notification sends when a task in its profile becomes overdue or due soon, or when an automation calls the notify action.
