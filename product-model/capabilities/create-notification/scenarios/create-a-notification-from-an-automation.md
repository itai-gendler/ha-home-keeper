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
- text: The Product saves the notification with its allowed targets
  kind: product
  actor: automation
  entities:
  - {entity: notification, effect: creates, facts: [Name, Profile, Send to]}
  contexts:
    services: {place: services}
---

# Create a notification from an automation

## Trigger

An automation calls the set options action with a new notification.

## Outcome

The notification is saved.
