---
kind: alternative
routes:
  panel: Panel
steps:
- text: A problem sensor that no exclusion removes reports a problem
  kind: condition
  unattended: true
  entities:
  - {entity: home-keeper-settings, effect: reads, facts: [Problem sensor sync, Problem sensor exclusions]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product arms the task that mirrors the sensor, creating it with the sensor's device and area when it is missing
  kind: product
  entities:
  - {entity: task, effect: changes, from: Monitored, to: Scheduled, facts: [Due date]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Arm a synced problem-sensor task

## Trigger

A problem binary sensor reports a problem while Problem sensor sync is on.

## Outcome

The synced task is overdue.
