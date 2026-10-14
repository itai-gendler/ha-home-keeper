---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the skip task action
  kind: actor
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: []}
  - {entity: skip, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product records the skip and advances the task
  kind: product
  actor: automation
  entities:
  - {entity: skip, effect: creates, facts: [Skipped at, Note]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    services: {place: services}
---

# Skip a task from an automation

## Trigger

An automation calls the skip task action.

## Outcome

The task moves to its next occurrence.
