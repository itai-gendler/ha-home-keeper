---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the delete completion action
  kind: actor
  actor: automation
  entities:
  - {entity: completion, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product removes the completion
  kind: product
  actor: automation
  entities:
  - {entity: completion, effect: removes}
  contexts:
    services: {place: services}
---

# Delete a completion from an automation

## Trigger

An automation calls the delete completion action.

## Outcome

The completion is gone.
