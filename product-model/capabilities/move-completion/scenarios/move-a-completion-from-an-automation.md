---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the move completion action
  kind: actor
  actor: automation
  entities:
  - {entity: completion, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product moves the completion
  kind: product
  actor: automation
  entities:
  - {entity: completion, effect: changes, facts: [Completed at]}
  contexts:
    services: {place: services}
---

# Move a completion from an automation

## Trigger

An automation calls the move completion action.

## Outcome

The completion has the new date.
