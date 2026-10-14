---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update asset action with a new part
  kind: actor
  actor: automation
  entities:
  - {entity: part, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product adds the part
  kind: product
  actor: automation
  entities:
  - {entity: part, effect: creates, facts: [Name, Kind, Stock, Reorder at]}
  contexts:
    services: {place: services}
---

# Add a part from an automation

## Trigger

An automation calls the update asset action with a new part.

## Outcome

The part is on the appliance.
