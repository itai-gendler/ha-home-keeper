---
kind: alternative
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
- text: The Product records the completion and moves the task past the date it showed to the next occurrence of its schedule
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Complete a task on a fixed schedule

## Trigger

A household member completes medicine due each day at 8am.

## Outcome

The task is due at the next occurrence; the dates that follow do not move.

## Edge cases

- After a snooze or Due today, the next occurrence is after the date the task showed.
