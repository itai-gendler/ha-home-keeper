---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update task action with a task id or name and the changed fields
  kind: actor
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product merges the fields into the task
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: changes, facts: [Name, Labels, Area, Active season, Snooze length, Links to show on card]}
  contexts:
    services: {place: services}
---

# Update a task from an automation

## Trigger

An automation calls the update task action.

## Outcome

The task has the fields the call sent; the others keep their values.

## Edge cases

- The name and tag of a task an appliance part makes are refused; the part sets them.
