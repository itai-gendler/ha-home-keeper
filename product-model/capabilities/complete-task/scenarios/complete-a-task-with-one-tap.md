---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses Done
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product records the completion now and moves the due date one interval after it
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product shows a message naming the task with Undo
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Complete a task with one tap

## Trigger

A household member presses Done on a one-tap task.

## Outcome

The completion is in the history and the task is due one interval later.

## Decision points

### Due time

Which Due time is set?

- At the time of completion → the next due date keeps the time of day of the completion
- At a set time → the next due date is at the set time on that day
