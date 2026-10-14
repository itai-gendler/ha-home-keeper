---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses Snooze and picks a duration or a date
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Due date, Snooze length]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product shows the new due date and applies it
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Snooze a task in the panel

## Trigger

A household member presses Snooze.

## Outcome

The task is due at the new date; its schedule is unchanged.

## Edge cases

- A date that is not after the start is refused.
- With a set due time, a snooze of a repeating task ends at the set time.
