---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin presses Start counting and enters In stock and Reorder at
  kind: actor
  actor: admin
  entities:
  - {entity: part, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product saves the stock fields
  kind: product
  actor: admin
  entities:
  - {entity: part, effect: changes, facts: [Stock, Reorder at, Stock unit, Used per completion, Restock quantity, Auto-create buy task]}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Start counting a managed part

## Trigger

An admin presses Start counting on a part a companion owns.

## Outcome

The part tracks stock; the owner's fields stay read-only.
