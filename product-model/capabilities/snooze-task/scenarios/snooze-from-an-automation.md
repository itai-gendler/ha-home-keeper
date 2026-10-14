---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the snooze task action with hours or an exact date
  kind: actor
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product moves the due date, one day when neither is given
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    services: {place: services}
---

# Snooze a task from an automation

## Trigger

An automation calls the snooze task action.

## Outcome

The task is due later.
