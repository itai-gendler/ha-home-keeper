---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin changes the urgency, channel and buttons
  kind: actor
  actor: admin
  entities:
  - {entity: notification, effect: reads, facts: [Urgency, Notification channel, Buttons]}
  contexts:
    panel: {place: 'panel::administration::notifications'}
- text: The Product saves the notification
  kind: product
  actor: admin
  entities:
  - {entity: notification, effect: changes, facts: [Urgency, Notification channel, Buttons]}
  contexts:
    panel: {place: 'panel::administration::notifications'}
---

# Edit a notification in the panel

## Trigger

An admin changes a notification.

## Outcome

The notification sends with the new settings.

## Edge cases

- An Android channel keeps the settings it was created with; a new urgency needs a new channel name.
