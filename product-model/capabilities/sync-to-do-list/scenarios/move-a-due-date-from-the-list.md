---
kind: alternative
routes:
  panel: Panel
steps:
- text: An item's due date changed on the list, with Two-way sync on
  kind: condition
  unattended: true
  entities:
  - {entity: profile, effect: reads, facts: [Two-way sync]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product moves the task to that date as a snooze does
  kind: product
  entities:
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Move a task's due date from the list

## Trigger

Someone changes an item's due date on a list that gives each item an id.

## Outcome

The task is due on that date with its time of day and schedule.

## Edge cases

- With Two-way sync off, Home Keeper puts its own due date back.
