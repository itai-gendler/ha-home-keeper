---
kind: alternative
routes:
  panel: Panel
steps:
- text: A part's stock is above Reorder at, or Auto-create buy task is off, while its Buy task is open
  kind: condition
  unattended: true
  entities:
  - {entity: part, effect: reads, facts: [Stock, Reorder at, Auto-create buy task]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product removes the Buy task
  kind: product
  entities:
  - {entity: task, effect: removes, from: Scheduled}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# The part is restocked another way

## Trigger

The stock rises above the threshold by hand, or Auto-create buy task is turned off.

## Outcome

The Buy task is gone.
