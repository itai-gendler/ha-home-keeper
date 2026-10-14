---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member selects a consumable part
  kind: actor
  actor: household-member
  entities:
  - {entity: part, effect: reads, facts: [Name, Stock]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product links the task to the part
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: changes, facts: [Linked consumable]}
  - {entity: part, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Link a task to a consumable

## Trigger

A household member selects a part in Linked consumable.

## Outcome

Each completion of the task draws the part's stock.
