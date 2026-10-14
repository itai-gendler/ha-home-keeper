---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the list tasks action
  kind: actor
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product answers with every task and its fields
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: [Name, Due date, Schedule kind, Labels, Area, Device]}
  contexts:
    services: {place: services}
---

# List tasks from an automation

## Trigger

An automation calls the list tasks action.

## Outcome

The automation receives every task.
