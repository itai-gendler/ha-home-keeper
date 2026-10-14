---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the export appliance report action
  kind: actor
  actor: automation
  entities:
  - {entity: appliance, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product returns the report
  kind: product
  actor: automation
  entities:
  - {entity: appliance, effect: reads, facts: [Name, Replacement cost]}
  contexts:
    services: {place: services}
---

# Export the report from an automation

## Trigger

An automation calls the export appliance report action.

## Outcome

The automation receives the report.
