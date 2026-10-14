---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the delete asset action
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product removes the appliance with its parts and documents
  kind: product
  actor: automation
  entities:
  - {entity: appliance, effect: removes, from: Active}
  - {entity: part, effect: removes, with: appliance}
  - {entity: appliance-document, effect: removes, with: appliance}
  contexts:
    services: {place: services}
---

# Delete an appliance from an automation

## Trigger

An automation calls the delete asset action.

## Outcome

The appliance and its files are gone; child appliances stand alone.
