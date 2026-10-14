---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the set options action with the option keys
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product merges the options, saves them and applies them before the call returns
  kind: product
  actor: automation
  entities:
  - {entity: home-keeper-settings, effect: changes, facts: [Snooze on, Skip on, Due today on]}
  contexts:
    services: {place: services}
---

# Change the snooze, skip and due today settings from an automation

## Trigger

An automation calls the set options action.

## Outcome

The turned-off action is gone from the panel, the card and the notification buttons.
