---
kind: primary
routes:
  panel: Panel
steps:
- text: A Buy task is open and a shopping list is set
  kind: condition
  unattended: true
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: home-keeper-settings, effect: reads, facts: [Shopping list, Line text on list]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product adds an item with the verb or product-only line and the amount to buy
  kind: product
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: part, effect: reads, facts: [Name, Restock quantity, Stock unit]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Add an item for each buy task

## Trigger

A Buy task opens while a shopping list is set.

## Outcome

The shopping list has an item for it.

## Edge cases

- A name someone gives the item on the list is kept.
