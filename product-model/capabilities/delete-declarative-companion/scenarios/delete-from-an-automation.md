---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the delete declarative companion action
  kind: actor
  actor: automation
  entities:
  - {entity: declarative-companion, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product removes it with its tasks
  kind: product
  actor: automation
  entities:
  - {entity: declarative-companion, effect: removes, from: 'On'}
  - {entity: task, effect: removes, from: Monitored, with: declarative-companion}
  contexts:
    services: {place: services}
---

# Delete a declarative companion from an automation

## Trigger

An automation calls the delete declarative companion action.

## Outcome

It is gone.
