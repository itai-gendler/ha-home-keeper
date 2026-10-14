---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses delete on a skip in the history
  kind: actor
  actor: household-member
  entities:
  - {entity: skip, effect: reads, facts: [Skipped at]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product removes the skip and puts back the due date when it was the latest
  kind: product
  actor: household-member
  entities:
  - {entity: skip, effect: removes}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Delete a skip in the history

## Trigger

A household member presses delete on a skip row.

## Outcome

The skip is gone.
