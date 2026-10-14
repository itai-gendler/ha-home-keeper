---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin adds a notification, picks a profile and devices, and sets the style and triggers
  kind: actor
  actor: admin
  entities:
  - {entity: profile, effect: reads, facts: [Name]}
  - {entity: notification, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::administration::notifications'}
- text: The Product saves the notification, keeping only mobile app devices and persistent notification as targets
  kind: product
  actor: admin
  entities:
  - {entity: notification, effect: creates, facts: [Name, Profile, Send to, Buttons, Snooze duration, Style, Notification channel, Urgency, Notification icon, Accent color, Send when overdue, Send when due soon]}
  contexts:
    panel: {place: 'panel::administration::notifications'}
---

# Create a notification in the panel

## Trigger

An admin adds a notification in Settings → Notifications.

## Outcome

The notification is saved.
