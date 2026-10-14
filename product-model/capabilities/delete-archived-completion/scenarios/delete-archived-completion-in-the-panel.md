---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses delete on a history row of a deleted task and confirms
  kind: actor
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: [Maintenance history]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product removes the entry from the appliance's history
  kind: product
  actor: admin
  entities:
  - {entity: appliance, effect: changes, facts: [Maintenance history]}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Delete an archived completion in the panel

## Trigger

An admin deletes a history row of a deleted task.

## Outcome

The entry is gone from the appliance's history.
