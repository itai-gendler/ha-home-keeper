---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the add asset action
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product creates the appliance
  kind: product
  actor: automation
  entities:
  - {entity: appliance, effect: creates, to: Active, facts: [Name, Manufacturer, Model, Serial number, External id]}
  contexts:
    services: {place: services}
---

# Create an appliance from an automation

## Trigger

An automation calls the add asset action.

## Outcome

The appliance exists with its device page.
