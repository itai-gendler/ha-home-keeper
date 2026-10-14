---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member presses Delete and confirms
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product removes the task with its completions, skips and photos
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: removes, from: Scheduled}
  - {entity: completion, effect: removes, with: task}
  - {entity: skip, effect: removes, with: task}
  - {entity: task-photo, effect: removes, with: task}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Delete a task in the panel

## Trigger

A household member presses Delete in a task's form.

## Outcome

The task and its photos are gone.

## Edge cases

- A task an appliance part or a low-stock part makes is refused; change the part instead.
