---
kind: validation
routes:
  panel: Panel
steps:
- text: The Household member presses Done
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The task requires a tag scan
  kind: condition
  entities:
  - {entity: task, effect: reads, facts: [Require tag scan]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product refuses and asks for a scan of the tag
  kind: product
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::task'}
---

# Refuse Done on a scan-only task

## Trigger

A household member presses Done on a task that requires a tag scan.

## Outcome

No completion is recorded; the task waits for a scan.
