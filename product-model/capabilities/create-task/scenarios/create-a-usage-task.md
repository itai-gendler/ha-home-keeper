---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member selects a meter sensor, a target and an optional starting reading
  kind: actor
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product creates the task with the starting reading, or the current reading, as its baseline
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: creates, to: Monitored, facts: [Name, Schedule kind, Sensor, Trigger mode, Trigger condition, Combined cadence, Meter baseline]}
  contexts:
    panel: {place: 'panel::household::new-task'}
---

# Create a usage task

## Trigger

A household member selects Based on a sensor with Usage or meter.

## Outcome

The task counts usage from its baseline and becomes due when the target is reached.

## Decision points

### Also come due on a schedule

Is Also come due on a schedule on?

- on, Whichever comes first → the task is due at the target or when the period elapses
- on, Both must be met → the task is due only when both are met
- off → only the target makes the task due
