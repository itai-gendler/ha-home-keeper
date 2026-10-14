---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member selects an entity, the mode, the condition and an optional hold
  kind: actor
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product creates a monitored task bound to the entity
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: creates, to: Monitored, facts: [Name, Schedule kind, Sensor, Trigger mode, Trigger condition, Clear when back to normal]}
  contexts:
    panel: {place: 'panel::household::new-task'}
---

# Create a task that watches a condition

## Trigger

A household member selects Based on a sensor with Threshold, State or Availability.

## Outcome

The task is monitored and arms when the condition holds.
