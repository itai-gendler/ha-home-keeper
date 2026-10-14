---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update task action with enabled on
  kind: actor
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product enables the task
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: changes, from: Disabled, to: Scheduled, facts: []}
  contexts:
    services: {place: services}
---

# Enable a task from an automation

## Trigger

An automation calls update task with enabled on.

## Outcome

The task is back.

## Edge cases

- Pairing it with Due today gives a clean start date.
