---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin opens an archived appliance and presses Restore
  kind: actor
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product restores the appliance
  kind: product
  actor: admin
  entities:
  - {entity: appliance, effect: changes, from: Archived, to: Active, facts: []}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Restore an appliance in the panel

## Trigger

An admin presses Restore on an archived appliance.

## Outcome

The appliance is active again.
