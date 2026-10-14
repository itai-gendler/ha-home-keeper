---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member presses Done on the use task
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product records the use; the replacement task becomes due once the count reaches the target
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Counted, to: Counted, facts: [Last completed]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Count a use

## Trigger

A household member completes the use task of a counted wear item.

## Outcome

One more use is counted toward the replacement.
