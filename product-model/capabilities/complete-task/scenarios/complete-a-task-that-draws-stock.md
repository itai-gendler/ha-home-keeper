---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member presses Done
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Linked consumable]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product records the completion with the stock it drew and reschedules the task
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at, Stock drawn]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product takes the per-use amount off the part's stock and sets its last replaced date
  kind: product
  actor: household-member
  entities:
  - {entity: part, effect: changes, facts: [Stock, Last replaced]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Complete a task that draws spare stock

## Trigger

A household member completes a task linked to a consumable or made by a wear item.

## Outcome

The part's stock goes down by its per-use amount.

## Edge cases

- When stock drops to the reorder threshold, a low-stock event fires.
