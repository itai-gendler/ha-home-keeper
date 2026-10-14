---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses edit on a skip in the history
  kind: actor
  actor: household-member
  entities:
  - {entity: skip, effect: reads, facts: [Skipped at]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product saves the skip
  kind: product
  actor: household-member
  entities:
  - {entity: skip, effect: changes, facts: [Note, Who]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Edit a skip in the history

## Trigger

A household member presses edit on a skip row.

## Outcome

The skip is updated.
