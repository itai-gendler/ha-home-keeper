---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses Skip and adds an optional note and person
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Due date]}
  - {entity: skip, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product records the skip and advances the task one occurrence
  kind: product
  actor: household-member
  entities:
  - {entity: skip, effect: creates, facts: [Skipped at, Note, Who]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Skip a task in the panel

## Trigger

A household member presses Skip.

## Outcome

The task moves to its next occurrence and the skip is in the history.

## Edge cases

- An overdue task on a fixed schedule moves to its first occurrence after now, passing over every missed occurrence.
