---
kind: validation
routes:
  panel: Panel
steps:
- text: The Admin picks a parent appliance that is this appliance or one of its subdevices
  kind: actor
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: [Parent appliance]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product refuses, because an appliance cannot sit under itself
  kind: product
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Refuse an appliance under itself

## Trigger

An admin picks a parent that sits under this appliance.

## Outcome

Nothing changes.
