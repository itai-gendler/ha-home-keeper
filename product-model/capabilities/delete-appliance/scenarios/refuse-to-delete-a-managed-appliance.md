---
kind: validation
routes:
  panel: Panel
steps:
- text: The Admin presses Delete on a managed appliance
  kind: actor
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: [Managed by]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: A loaded companion protects the appliance
  kind: condition
  entities:
  - {entity: appliance, effect: reads, facts: [Managed by]}
  - {entity: companion, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product refuses and says to delete it from its owner
  kind: product
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Refuse to delete a protected appliance

## Trigger

An admin deletes an appliance a loaded companion protects.

## Outcome

The appliance stays and the message names the owner.
