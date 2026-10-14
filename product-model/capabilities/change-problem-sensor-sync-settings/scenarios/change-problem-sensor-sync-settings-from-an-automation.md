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
  - {entity: home-keeper-settings, effect: changes, facts: [Problem sensor sync, Problem sensor exclusions]}
  contexts:
    services: {place: services}
---

# Change the problem sensor sync settings from an automation

## Trigger

An automation calls the set options action.

## Outcome

Each problem sensor that is not excluded has a task that arms while it reports a problem.
