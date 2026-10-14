---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the add declarative companion action
  kind: actor
  actor: automation
  entities:
  - {entity: declarative-companion, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product saves it and opens its tasks
  kind: product
  actor: automation
  entities:
  - {entity: declarative-companion, effect: creates, to: 'On', facts: [Name, Entity filters, Trigger mode, Trigger condition]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
---

# Add a declarative companion from an automation

## Trigger

An automation calls the add declarative companion action.

## Outcome

The declarative companion is saved.
