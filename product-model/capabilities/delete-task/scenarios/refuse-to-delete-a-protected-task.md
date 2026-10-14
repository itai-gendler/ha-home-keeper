---
kind: validation
routes:
  panel: Panel
steps:
- text: The Household member presses Delete on a protected task
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Managed by]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The task is deletion protected and its managing integration is loaded
  kind: condition
  entities:
  - {entity: task, effect: reads, facts: [Deletion protected, Managed by]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product refuses and says to delete it from its owner
  kind: product
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::task'}
---

# Refuse to delete a protected task

## Trigger

A household member deletes a task that a loaded companion protects.

## Outcome

The task stays and the message names the owner.
