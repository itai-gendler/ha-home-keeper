---
kind: validation
routes:
  panel: Panel
steps:
- text: The Household member tries to complete the task
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: Only the recovery of its condition completes the task
  kind: condition
  entities:
  - {entity: task, effect: reads, facts: [Completed by its condition]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product refuses and says the task clears when the condition recovers
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Refuse to complete a task its condition owns

## Trigger

A household member tries to complete a synced problem-sensor task or a task that clears itself on recovery.

## Outcome

No completion is recorded and the message says the condition must recover.
