---
type: messaging
actors:
- household-member
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/notifier.py
- kind: code
  role: implementation
  target: custom_components/home_keeper/notifications.py
- kind: doc
  role: intent
  target: docs/guide/views/notifications.md
---

# Mobile notifications

Actionable notifications on the Home Assistant companion app, with the Mark done, Snooze, Skip and
Open buttons.
