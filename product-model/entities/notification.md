---
domain: notifications
references:
- kind: doc
  role: intent
  target: docs/guide/views/notifications.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/notifications.py#normalize_notification
---

# Notification

A saved mobile notification about the due tasks of a profile.

## Information kept

- **Name** — its name
- **Profile** — the profile whose tasks it carries
- **Send to** — companion-app devices and persistent notification
- **Buttons** — which of Mark done, Snooze, Skip and Open it shows
- **Snooze duration** — how long its Snooze button snoozes
- **Style** — walk or digest
- **Notification channel** — the Android channel or iPhone thread
- **Urgency** — Quiet, Normal, High or Critical
- **Notification icon** — an mdi icon
- **Accent color** — the accent color
- **Send when overdue** — send when a task becomes overdue
- **Send when due soon** — send when a task becomes due soon
