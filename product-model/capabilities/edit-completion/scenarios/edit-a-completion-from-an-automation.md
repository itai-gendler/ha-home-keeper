---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update completion action with the completion time and new details
  kind: actor
  actor: automation
  entities:
  - {entity: completion, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product saves the details
  kind: product
  actor: automation
  entities:
  - {entity: completion, effect: changes, facts: [Note, Cost, Who]}
  contexts:
    services: {place: services}
---

# Edit a completion from an automation

## Trigger

An automation calls the update completion action.

## Outcome

The completion carries the new details.
