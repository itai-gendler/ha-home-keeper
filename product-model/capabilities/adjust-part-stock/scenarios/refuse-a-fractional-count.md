---
kind: validation
routes:
  panel: Panel
steps:
- text: The Admin types 1.5 for a part counted in whole spares
  kind: actor
  actor: admin
  entities:
  - {entity: part, effect: reads, facts: [Stock]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product refuses the value
  kind: product
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Refuse a fraction of a counted part

## Trigger

An admin types a fraction for a part with no unit and no per-use amount.

## Outcome

The stock is unchanged.
