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
  - {entity: home-keeper-settings, effect: changes, facts: [Due time]}
  contexts:
    services: {place: services}
---

# Change the due time settings from an automation

## Trigger

An automation calls the set options action.

## Outcome

Each repeating task that is due later is due at the set time on its date; a task that is due now stays due now.
