---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses move date and picks a new date
  kind: actor
  actor: household-member
  entities:
  - {entity: completion, effect: reads, facts: [Completed at]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product moves the completion and works out the due date again from the latest completion
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: changes, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Move a history entry

## Trigger

A household member presses move date on a history row.

## Outcome

The completion has the new date; the due date follows when it is the latest.

## Edge cases

- Moving an older entry keeps the due date, a snooze and a skip.
