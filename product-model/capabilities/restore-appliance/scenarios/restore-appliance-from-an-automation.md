---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the restore asset action
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product restores the appliance
  kind: product
  actor: automation
  entities:
  - {entity: appliance, effect: changes, from: Archived, to: Active, facts: []}
  contexts:
    services: {place: services}
---

# Restore an appliance from an automation

## Trigger

An automation calls the restore asset action.

## Outcome

The appliance is active again.
