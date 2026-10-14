---
kind: alternative
routes:
  panel: Panel
steps:
- text: The reading minus the baseline reaches the target, or the combined cadence elapses
  kind: condition
  unattended: true
  entities:
  - {entity: task, effect: reads, facts: [Meter baseline, Trigger condition, Combined cadence]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product makes the task due
  kind: product
  entities:
  - {entity: task, effect: changes, from: Monitored, to: Scheduled, facts: [Due date]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Arm a usage task at its target

## Trigger

The meter of a usage task advances by its target from the baseline.

## Outcome

The task is due.

## Edge cases

- A reading below the baseline after a meter reset re-anchors the baseline.
