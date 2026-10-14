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
  - {entity: home-keeper-settings, effect: changes, facts: [Shopping list, Line text on list]}
  contexts:
    services: {place: services}
---

# Change the shopping list settings from an automation

## Trigger

An automation calls the set options action.

## Outcome

Buy tasks are synced to the chosen list with the chosen line text; clearing the list turns the sync off.
