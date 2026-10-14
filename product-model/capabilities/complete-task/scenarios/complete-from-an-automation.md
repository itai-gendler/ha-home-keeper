---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the complete task action with a note, cost, photo or person
  kind: actor
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product records the completion and reschedules the task
  kind: product
  actor: automation
  entities:
  - {entity: completion, effect: creates, facts: [Completed at, Note, Cost, Photo, Who]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    services: {place: services}
---

# Complete a task from an automation

## Trigger

An automation calls the complete task action.

## Outcome

The task is completed with the details the call passed.
