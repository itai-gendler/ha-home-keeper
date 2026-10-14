---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member presses Done on a Buy task in the Shopping section
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product records the completion and adds the restock quantity to the part's stock
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Completed, facts: [Due date, Last completed]}
  - {entity: part, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product adds the restock quantity to the part
  kind: product
  actor: household-member
  entities:
  - {entity: part, effect: changes, facts: [Stock]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Complete a buy task

## Trigger

A household member completes a Buy part task.

## Outcome

The part is restocked by its restock quantity.

## Edge cases

- If the stock stays at or below the threshold, the reminder remains.
