---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses delete on a completion and confirms
  kind: actor
  actor: household-member
  entities:
  - {entity: completion, effect: reads, facts: [Completed at]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product removes the completion, returns the stock it drew and works out the due date again
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: removes}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Delete a history entry

## Trigger

A household member deletes a history row.

## Outcome

The completion is gone and any stock it drew is back.
