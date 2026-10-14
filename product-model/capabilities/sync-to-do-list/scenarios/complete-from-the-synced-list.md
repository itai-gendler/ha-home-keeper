---
kind: alternative
routes:
  panel: Panel
steps:
- text: An item Home Keeper added is marked complete on the list, with Two-way sync on
  kind: condition
  unattended: true
  entities:
  - {entity: profile, effect: reads, facts: [Two-way sync, Treat removed items as completed]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product completes the task and leaves the item complete on the list
  kind: product
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Complete a task from its synced list

## Trigger

Someone checks an item Home Keeper added.

## Outcome

The task is completed once, however many lists show it.

## Edge cases

- A scan-only task, or one its condition owns, is not completed from the list; the item is added again on the next sync.
