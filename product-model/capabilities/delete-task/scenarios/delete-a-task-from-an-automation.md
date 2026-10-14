---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the delete task action with a task id
  kind: actor
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product removes the task
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: removes, from: Scheduled}
  - {entity: completion, effect: removes, with: task}
  - {entity: skip, effect: removes, with: task}
  contexts:
    services: {place: services}
---

# Delete a task from an automation

## Trigger

An automation calls the delete task action.

## Outcome

The task is gone.

## Edge cases

- An unknown id succeeds, so an integration can delete every id it stored; an unknown name is refused.
