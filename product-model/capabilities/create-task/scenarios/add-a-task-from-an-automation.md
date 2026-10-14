---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the add task action with a name and optional schedule
  kind: actor
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product creates the task, a one-off due now when no schedule is given, and returns its id
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Schedule kind, Due date, Last completed, External id]}
  contexts:
    services: {place: services}
---

# Add a task from an automation

## Trigger

An automation calls the add task action.

## Outcome

The task exists and the action returns its id.

## Edge cases

- An area that Home Assistant does not have is refused.
- A source namespace that Home Keeper reserves for its own tasks is refused.
