---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member presses Duplicate
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product opens the create form with the task's values, without its history, starting reading, tag, required fields, integration chips or source
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name, Notes, Schedule kind, Interval, Fixed start, Device, Area, Labels, Snooze length]}
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Household member changes the values and presses Create
  kind: actor
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product creates the copy
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Notes, Schedule kind, Interval, Due date, Device, Area, Labels, On completion]}
  contexts:
    panel: {place: 'panel::household::new-task'}
---

# Duplicate a task

## Trigger

A household member presses Duplicate on a task's page.

## Outcome

A new task with the copied values exists after Create.

## Edge cases

- Duplicate is disabled for a task another owner manages, and pressing it names the owner.
