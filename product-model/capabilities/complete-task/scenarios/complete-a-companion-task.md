---
kind: alternative
routes:
  services: Services
steps:
- text: The Companion calls the complete task action for its armed task
  kind: actor
  actor: companion
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product records the completion and returns the task to monitored
  kind: product
  actor: companion
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Monitored, facts: [Due date, Last completed]}
  contexts:
    services: {place: services}
---

# Complete a task its companion reports done

## Trigger

A companion reports that the work on its triggered task is done.

## Outcome

The task returns to monitored with the completion in its history.
