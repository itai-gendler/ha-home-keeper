---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update skip action
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
  - {entity: skip, effect: changes, facts: [Note, Who]}
  contexts:
    services: {place: services}
---

# Edit a skip from an automation

## Trigger

An automation calls the update skip action.

## Outcome

The skip is updated.
