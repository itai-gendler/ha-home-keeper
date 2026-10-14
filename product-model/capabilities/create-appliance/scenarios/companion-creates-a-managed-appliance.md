---
kind: alternative
routes:
  services: Services
steps:
- text: The Companion calls the add asset action with its ownership block and parts
  kind: actor
  actor: companion
  entities:
  - {entity: part, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product creates the appliance managed by the companion
  kind: product
  actor: companion
  entities:
  - {entity: appliance, effect: creates, to: Active, facts: [Name, Managed by]}
  - {entity: part, effect: creates, facts: [Name, Kind], with: appliance}
  contexts:
    services: {place: services}
---

# A companion creates a managed appliance

## Trigger

A companion such as a battery glue integration creates its appliance.

## Outcome

The appliance shows a Managed by chip.
