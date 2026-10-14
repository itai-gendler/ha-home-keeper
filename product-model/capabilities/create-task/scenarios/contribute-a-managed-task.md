---
kind: alternative
routes:
  services: Services
steps:
- text: The Companion calls the add task action with its ownership block and integration chips
  kind: actor
  actor: companion
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product creates the task managed by the companion, triggered tasks dormant until armed
  kind: product
  actor: companion
  entities:
  - {entity: task, effect: creates, to: Monitored, facts: [Name, Schedule kind, Managed by, Deletion protected, Integration chips, Completed by its condition]}
  contexts:
    services: {place: services}
---

# Contribute a managed task

## Trigger

A companion adds a task it owns.

## Outcome

The task shows a Managed by chip and keeps the fields its owner locks.

## Edge cases

- A protected task without the companion's config entry is refused.
