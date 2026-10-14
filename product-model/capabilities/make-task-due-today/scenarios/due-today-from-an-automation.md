---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the set due today action
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product moves the due date to today
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    services: {place: services}
---

# Make a task due today from an automation

## Trigger

An automation, such as one that enables seasonal tasks, calls the set due today action.

## Outcome

The task is due today.
