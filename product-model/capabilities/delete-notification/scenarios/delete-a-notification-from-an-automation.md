---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the set options action without the notification
  kind: actor
  actor: automation
  entities:
  - {entity: notification, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product removes it
  kind: product
  actor: automation
  entities:
  - {entity: notification, effect: removes}
  contexts:
    services: {place: services}
---

# Delete a notification from an automation

## Trigger

An automation calls the set options action without it.

## Outcome

The notification is gone.
