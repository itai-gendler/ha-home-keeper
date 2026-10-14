---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update task action with enabled off
  kind: actor
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product disables the task and keeps its due date
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: changes, from: Scheduled, to: Disabled, facts: []}
  contexts:
    services: {place: services}
---

# Disable tasks from an automation

## Trigger

An automation that follows a helper, such as the pool being closed, calls update task with enabled off.

## Outcome

The task leaves the to-do list, calendar, device page, profiles, notifications and card.
