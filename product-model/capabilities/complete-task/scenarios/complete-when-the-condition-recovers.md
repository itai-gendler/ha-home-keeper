---
kind: primary
routes:
  panel: Panel
steps:
- text: The entity of an armed task with Clear when back to normal, a declarative companion with Auto-clear, or a synced problem sensor returns to normal
  kind: condition
  unattended: true
  entities:
  - {entity: task, effect: reads, facts: [Clear when back to normal, Sensor]}
  - {entity: declarative-companion, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product records a completion and returns the task to monitored
  kind: product
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Monitored, facts: [Due date, Last completed]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Complete a task when its condition recovers

## Trigger

The entity of an armed task that clears itself returns to normal.

## Outcome

The task is completed and monitored again.

## Edge cases

- A template that does not render decides nothing, so it never completes a task.
