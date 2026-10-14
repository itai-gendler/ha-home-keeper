---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses Due today
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Due date]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product moves the due date to today at once, with no dialog and no completion
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  - {entity: completion, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Press Due today

## Trigger

A household member presses Due today on a task that is due later.

## Outcome

The task is due today.

## Edge cases

- A task already due or overdue does not offer Due today.
