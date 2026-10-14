---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Archive
  kind: actor
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product archives the appliance
  kind: product
  actor: admin
  entities:
  - {entity: appliance, effect: changes, from: Active, to: Archived, facts: []}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Archive an appliance in the panel

## Trigger

An admin presses Archive on an appliance.

## Outcome

The appliance is in the Archived list.
