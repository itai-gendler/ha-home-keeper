---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the delete archived completion action
  kind: actor
  actor: automation
  entities:
  - {entity: completion, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product removes the entry
  kind: product
  actor: automation
  entities:
  - {entity: appliance, effect: changes, facts: [Maintenance history]}
  contexts:
    services: {place: services}
---

# Delete an archived completion from an automation

## Trigger

An automation calls the delete archived completion action.

## Outcome

The entry is gone from the appliance's history.
