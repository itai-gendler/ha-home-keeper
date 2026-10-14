---
kind: primary
routes:
  services: Services
steps:
- text: The Companion calls the trigger task action for its task
  kind: actor
  actor: companion
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product arms the task, due now
  kind: product
  actor: companion
  entities:
  - {entity: task, effect: changes, from: Monitored, to: Scheduled, facts: [Due date]}
  contexts:
    services: {place: services}
---

# A companion arms its triggered task

## Trigger

A companion's condition becomes true, such as a low battery.

## Outcome

The task is due now with a Managed by chip.
