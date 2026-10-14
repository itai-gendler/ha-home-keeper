---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member selects Repeats on a fixed schedule with a frequency and a start date and time
  kind: actor
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product creates the task, due at the first occurrence at or after now
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Schedule kind, Interval, Fixed start, Due date, Active season]}
  contexts:
    panel: {place: 'panel::household::new-task'}
---

# Create a task on a fixed schedule

## Trigger

A household member creates a task such as medicine every day at 8am.

## Outcome

The task is due at the next occurrence on its calendar schedule.
