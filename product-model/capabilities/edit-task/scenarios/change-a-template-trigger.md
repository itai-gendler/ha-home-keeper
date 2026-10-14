---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin changes the template and saves
  kind: actor
  actor: admin
  entities:
  - {entity: task, effect: reads, facts: [Trigger template]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product checks the template compiles and saves it, and reads the entity against the new condition
  kind: product
  actor: admin
  entities:
  - {entity: task, effect: changes, facts: [Trigger template]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Change a task's template trigger

## Trigger

An admin changes the template of a template task.

## Outcome

The task arms while the new template renders true.

## Edge cases

- A household member sees the template locked.
