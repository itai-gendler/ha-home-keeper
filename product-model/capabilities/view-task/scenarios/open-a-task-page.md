---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member selects a task in the list
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product opens the task's page on its Schedule tab with its photos and linked consumable
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Schedule kind, Interval, Fixed start, Due date, Last completed, Active season, Sensor, Trigger mode, Trigger condition, Meter baseline, Linked consumable]}
  - {entity: task-photo, effect: reads, facts: [Image, Cover]}
  - {entity: part, effect: reads, facts: [Name, Stock]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Household member opens the History tab
  kind: actor
  actor: household-member
  entities:
  - {entity: completion, effect: reads, facts: [Completed at, Note, Cost, Photo, Who, Reading]}
  - {entity: skip, effect: reads, facts: [Skipped at, Note, Who]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product lists the completions and skips, marks each skip, and shows the last, average, shortest and longest interval of usage
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: reads, facts: [Completed at, Reading]}
  - {entity: skip, effect: reads, facts: [Skipped at]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Open a task's page

## Trigger

A household member selects a task.

## Outcome

The household member reads the task's schedule, notes, photos and history.

## Edge cases

- A usage task shows the remaining usage, such as 180 h to go.
- A meter reset pair is left out of the usage intervals.
