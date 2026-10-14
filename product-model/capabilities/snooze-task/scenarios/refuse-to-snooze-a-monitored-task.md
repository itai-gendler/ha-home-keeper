---
kind: validation
routes:
  panel: Panel
steps:
- text: The Household member tries to snooze a monitored task
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The task has no due date
  kind: condition
  entities:
  - {entity: task, effect: reads, facts: [Due date]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product refuses, because there is no due date to move
  kind: product
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::task'}
---

# Refuse to snooze a task with no due date

## Trigger

A household member snoozes a task that waits for its condition.

## Outcome

Nothing changes.
