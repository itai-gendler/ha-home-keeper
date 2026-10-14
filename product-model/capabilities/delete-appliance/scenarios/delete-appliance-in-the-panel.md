---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Delete and confirms
  kind: actor
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product removes the appliance, its parts and documents, the tasks its parts made, and its device
  kind: product
  actor: admin
  entities:
  - {entity: appliance, effect: removes, from: Archived}
  - {entity: part, effect: removes, with: appliance}
  - {entity: appliance-document, effect: removes, with: appliance}
  - {entity: task, effect: removes, from: Scheduled, with: part}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Delete an appliance in the panel

## Trigger

An admin presses Delete on an appliance.

## Outcome

The appliance and its files are gone; child appliances stand alone.
