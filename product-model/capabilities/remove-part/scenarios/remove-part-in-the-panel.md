---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin removes a part in the appliance editor and presses Save
  kind: actor
  actor: admin
  entities:
  - {entity: part, effect: reads, facts: [Name]}
  - {entity: appliance, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product removes the part and the tasks it made
  kind: product
  actor: admin
  entities:
  - {entity: part, effect: removes}
  - {entity: task, effect: removes, from: Scheduled, with: part}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Remove a part in the panel

## Trigger

An admin removes a part.

## Outcome

The part is gone.
