---
kind: alternative
routes:
  services: Services
steps:
- text: The Household member runs a script that calls the complete task action
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product records the completion and reschedules the task
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    services: {place: services}
---

# Complete a task from a script a person runs

## Trigger

A household member runs a script that calls the complete task action.

## Outcome

The task is completed.
