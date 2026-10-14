---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the adjust part stock action with a delta
  kind: actor
  actor: automation
  entities:
  - {entity: part, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product moves the stock
  kind: product
  actor: automation
  entities:
  - {entity: part, effect: changes, facts: [Stock]}
  contexts:
    services: {place: services}
---

# Adjust part stock from an automation

## Trigger

An automation calls the adjust part stock action.

## Outcome

The part has the new stock.
