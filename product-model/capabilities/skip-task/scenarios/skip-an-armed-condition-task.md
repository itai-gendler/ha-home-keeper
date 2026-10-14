---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member presses Skip on an armed task
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: skip, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product records the skip with the reading and returns the task to monitored
  kind: product
  actor: household-member
  entities:
  - {entity: skip, effect: creates, facts: [Skipped at]}
  - {entity: task, effect: changes, from: Scheduled, to: Monitored, facts: [Due date, Meter baseline]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Skip an armed condition task

## Trigger

A household member skips an armed sensor-based task.

## Outcome

The task returns to monitored.
