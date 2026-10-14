---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the move skip action
  kind: actor
  actor: automation
  entities:
  - {entity: skip, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product saves the skip
  kind: product
  actor: automation
  entities:
  - {entity: skip, effect: changes, facts: [Skipped at]}
  contexts:
    services: {place: services}
---

# Move a skip from an automation

## Trigger

An automation calls the move skip action.

## Outcome

The skip is updated.
