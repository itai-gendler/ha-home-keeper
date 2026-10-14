---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses Edit and changes the fields
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name, Schedule kind, Interval]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Household member presses Save
  kind: actor
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product saves the task and works out its due date again when the schedule changed
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: changes, facts: [Name, Notes, Interval, Due date, Area, Labels, On completion, Required completion fields, NFC tag, Require tag scan, Snooze length]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Edit a task in the panel

## Trigger

A household member presses Edit on a task.

## Outcome

The task has the new values and its due date follows a changed schedule.

## Edge cases

- Require tag scan without a linked tag is refused.
- A field the managing owner locks is not offered.
