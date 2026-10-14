---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member opens the Tasks tab
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product lists each task with its due date, schedule kind, device, area, labels and integration chips, grouped by status
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name, Due date, Schedule kind, Device, Area, Labels, Integration chips, Managed by]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Household member types words in Search and picks a scope pill
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name, Device, Area]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product keeps the tasks that hold every word, ignoring accents, and counts each scope pill over them
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name, Device, Area, Managed by]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Browse the task list

## Trigger

A household member opens the Tasks tab.

## Outcome

The household member sees each task with its status and can narrow the list.

## Edge cases

- A disabled task shows only under All, in a Disabled section, with a Disabled label in place of its due date.
- A completed one-off task shows in a Completed section with its completion.
