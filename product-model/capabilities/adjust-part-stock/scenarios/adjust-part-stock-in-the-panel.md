---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses + or − on the In stock stepper, or types a value
  kind: actor
  actor: admin
  entities:
  - {entity: part, effect: reads, facts: [Stock, Stock unit]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product moves the stock by one spare, or one completion's amount for a measured part
  kind: product
  actor: admin
  entities:
  - {entity: part, effect: changes, facts: [Stock]}
  - {entity: completion, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Adjust part stock in the panel

## Trigger

An admin uses the In stock stepper on the Parts tab.

## Outcome

The part has the new stock.
