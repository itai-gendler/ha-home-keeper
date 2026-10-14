---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the archive asset action
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product archives the appliance
  kind: product
  actor: automation
  entities:
  - {entity: appliance, effect: changes, from: Active, to: Archived, facts: []}
  contexts:
    services: {place: services}
---

# Archive an appliance from an automation

## Trigger

An automation calls the archive asset action.

## Outcome

The appliance is in the Archived list.
