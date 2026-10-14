---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin selects Based on a sensor, Template, and writes a template
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product checks that the template compiles and creates the monitored task
  kind: product
  actor: admin
  entities:
  - {entity: task, effect: creates, to: Monitored, facts: [Name, Schedule kind, Sensor, Trigger mode, Trigger template]}
  contexts:
    panel: {place: 'panel::household::new-task'}
---

# Create a task with a template trigger

## Trigger

An admin picks Template as the trigger mode.

## Outcome

The task is monitored and arms while the template renders true.

## Edge cases

- A template that does not compile is refused.
