---
domain: notifications
availability:
- {place: 'panel::administration'}
- {place: services}
references:
- kind: doc
  role: intent
  target: docs/guide/views/notifications.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/notifications.py#split_targets
---

# Create a notification

Save a mobile notification: the profile it carries, the companion-app devices it goes to, its buttons, walk or digest style, channel, urgency, icon, color and triggers.
