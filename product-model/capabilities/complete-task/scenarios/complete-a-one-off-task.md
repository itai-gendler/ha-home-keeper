---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member presses Done on a one-off task
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Schedule kind]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product records the completion and moves the task to Completed with no due date
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Completed, facts: [Due date, Last completed]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Complete a one-off task

## Trigger

A household member completes a one-off task.

## Outcome

The task is in the Completed section and does not come back.
