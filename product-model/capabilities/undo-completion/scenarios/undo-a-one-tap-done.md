---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member selects Undo in the message
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product removes that completion, returns any stock it drew and restores the previous due date
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: removes}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Undo a one-tap Done

## Trigger

A household member selects Undo in the message after Done.

## Outcome

The completion is gone and the task is due when it was before.

## Edge cases

- Undo of a completed one-off task returns it to its due date.
