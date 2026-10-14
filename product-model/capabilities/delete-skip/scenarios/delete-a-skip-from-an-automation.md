---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the delete skip action
  kind: actor
  actor: automation
  entities:
  - {entity: skip, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product removes the skip
  kind: product
  actor: automation
  entities:
  - {entity: skip, effect: removes}
  contexts:
    services: {place: services}
---

# Delete a skip from an automation

## Trigger

An automation calls the delete skip action.

## Outcome

The skip is gone.
