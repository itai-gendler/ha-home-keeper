---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Test
  kind: actor
  actor: admin
  entities:
  - {entity: notification, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::administration::notifications'}
- text: The Product saves the notification
  kind: product
  actor: admin
  entities:
  - {entity: notification, effect: changes, facts: [Name]}
  contexts:
    panel: {place: 'panel::administration::notifications'}
- text: The Product sends it with the first due task of the profile, or All caught up
  kind: product
  actor: admin
  entities:
  - {entity: notification, effect: reads, facts: [Profile, Send to, Style]}
  - {entity: task, effect: reads, facts: [Name, Due date]}
  - {entity: profile, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::administration::notifications'}
---

# Press Test

## Trigger

An admin presses Test on a notification.

## Outcome

The phone receives the delivery the form shows.
