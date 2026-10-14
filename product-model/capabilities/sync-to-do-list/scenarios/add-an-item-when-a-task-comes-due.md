---
kind: primary
routes:
  panel: Panel
steps:
- text: A task matches a profile that syncs to a to-do list and comes into its tier
  kind: condition
  unattended: true
  entities:
  - {entity: profile, effect: reads, facts: [Include, To-do list]}
  - {entity: task, effect: reads, facts: [Due date]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product adds an item with the due date in the Home Assistant time zone and the notes
  kind: product
  entities:
  - {entity: task, effect: reads, facts: [Name, Due date, Notes]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Add an item when a task comes into the profile

## Trigger

A task comes into a synced profile's tier.

## Outcome

The list has an item with the task's due date and notes.

## Edge cases

- An item for a task that leaves the profile, is rescheduled or is disabled is removed.
- A name someone gives the item is kept.
