---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member opens the disabled task and presses Enable
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product enables the task
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: changes, from: Disabled, to: Scheduled, facts: []}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Enable a task in the panel

## Trigger

A household member opens a task in the Disabled section.

## Outcome

The task is back on every surface with its stored due date.
