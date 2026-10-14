---
kind: primary
routes:
  panel: Panel
steps:
- text: The bound entity meets the condition for the whole hold
  kind: condition
  unattended: true
  entities:
  - {entity: task, effect: reads, facts: [Sensor, Trigger mode, Trigger condition]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product sets the due date to now
  kind: product
  entities:
  - {entity: task, effect: changes, from: Monitored, to: Scheduled, facts: [Due date]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Arm a task when its sensor meets the condition

## Trigger

The entity a monitored task watches crosses its threshold, reaches its state or stays unavailable for the hold.

## Outcome

The task is due now on the to-do list, the panel and the device's overdue sensor.

## Edge cases

- A short recovery does not clear a threshold task.
- A state already true when Home Assistant starts does not arm the task again.
- A template that does not render, or renders a number, decides nothing.
