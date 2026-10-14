---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin deletes the notification
  kind: actor
  actor: admin
  entities:
  - {entity: notification, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::administration::notifications'}
- text: The Product removes it
  kind: product
  actor: admin
  entities:
  - {entity: notification, effect: removes}
  contexts:
    panel: {place: 'panel::administration::notifications'}
---

# Delete a notification in the panel

## Trigger

An admin deletes a notification.

## Outcome

The notification is gone.
