---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update asset action
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product saves the fields the call sent
  kind: product
  actor: automation
  entities:
  - {entity: appliance, effect: changes, facts: [Notes, Custom fields]}
  contexts:
    services: {place: services}
---

# Edit an appliance from an automation

## Trigger

An automation calls the update asset action.

## Outcome

The appliance has the new details.
