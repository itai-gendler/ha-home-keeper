---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses edit on a completion and changes its details
  kind: actor
  actor: household-member
  entities:
  - {entity: completion, effect: reads, facts: [Note, Cost, Who, Reading]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product saves the details and keeps the due date
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: changes, facts: [Note, Cost, Photo, Who, Reading]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Edit a history entry

## Trigger

A household member presses edit on a history row.

## Outcome

The completion carries the new details.

## Edge cases

- A new reading on the latest completion moves the meter baseline.
