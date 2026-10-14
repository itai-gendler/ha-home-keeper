---
kind: primary
routes:
  entities: Native entities
steps:
- text: The Household member checks the task's item on the Home Keeper to-do list
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    entities: {place: native-entities}
- text: The Product records the completion at once and reschedules the task
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    entities: {place: native-entities}
---

# Complete a task on the to-do list or device page

## Trigger

A household member checks a Home Keeper to-do item or presses Mark done on a device page.

## Outcome

The task is completed with no details.

## Edge cases

- The capture dialog and Require details apply only in the panel.
