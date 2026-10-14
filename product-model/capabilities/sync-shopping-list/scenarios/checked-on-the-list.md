---
kind: alternative
routes:
  panel: Panel
steps:
- text: An item Home Keeper added is marked complete on the shopping list
  kind: condition
  unattended: true
  entities:
  - {entity: home-keeper-settings, effect: reads, facts: [Shopping list]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product completes the Buy task and restocks the part
  kind: product
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Completed, facts: [Due date, Last completed]}
  - {entity: part, effect: changes, facts: [Stock]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# An item is checked on the list

## Trigger

Someone checks a buy item on the shopping list.

## Outcome

The Buy task is completed and the part restocked.
