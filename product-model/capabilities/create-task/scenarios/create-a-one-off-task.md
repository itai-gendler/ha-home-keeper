---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member selects Just once and a due date
  kind: actor
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product creates the task due on that date, today when none is given
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Schedule kind, Due date]}
  contexts:
    panel: {place: 'panel::household::new-task'}
---

# Create a one-off task

## Trigger

A household member selects Just once.

## Outcome

The task is due on the chosen date and does not repeat.
