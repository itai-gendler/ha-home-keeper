---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update declarative companion action
  kind: actor
  actor: automation
  entities:
  - {entity: declarative-companion, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product saves it
  kind: product
  actor: automation
  entities:
  - {entity: declarative-companion, effect: changes, facts: [Trigger condition]}
  contexts:
    services: {place: services}
---

# Edit a declarative companion from an automation

## Trigger

An automation calls the update declarative companion action.

## Outcome

It has the new settings.
