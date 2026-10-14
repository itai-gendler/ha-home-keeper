---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the set options action with the notifications list
  kind: actor
  actor: automation
  entities:
  - {entity: notification, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product saves the notification
  kind: product
  actor: automation
  entities:
  - {entity: notification, effect: changes, facts: [Send when overdue]}
  contexts:
    services: {place: services}
---

# Edit a notification from an automation

## Trigger

An automation calls the set options action.

## Outcome

The notification has the new settings.
