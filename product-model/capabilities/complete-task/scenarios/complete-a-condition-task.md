---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member presses Done on an armed task
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product records the completion with the current reading and returns the task to monitored
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at, Reading]}
  - {entity: task, effect: changes, from: Scheduled, to: Monitored, facts: [Due date, Last completed, Meter baseline]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Complete an armed condition task

## Trigger

A household member completes an armed sensor-based or triggered task.

## Outcome

The task returns to monitored until its condition holds again.

## Edge cases

- A usage task keeps Done while it counts; completing it early moves the meter.
