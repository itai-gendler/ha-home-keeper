---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses Add task
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Household member enters a name and selects the schedule that repeats after each done, with an interval
  kind: actor
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product creates the task, due now
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Notes, Schedule kind, Interval, Due date, Device, Area, Labels, On completion]}
  contexts:
    panel: {place: 'panel::household::new-task'}
---

# Create a task that repeats after each completion

## Trigger

A household member presses Add task.

## Outcome

A new task exists and is due now, one interval after each later completion.

## Edge cases

- A name that is empty is refused.
- An interval below 1 or above the largest interval is refused.
