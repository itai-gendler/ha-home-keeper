---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member presses Edit note and writes Markdown with a live preview
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Notes]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product saves the note
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: changes, facts: [Notes]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Edit a task's note inline

## Trigger

A household member presses Edit note on the task's Notes tab.

## Outcome

The note is saved as Markdown.

## Edge cases

- On a synced problem-sensor task the note stays with the sensor when the task clears, re-arms or is recreated.
