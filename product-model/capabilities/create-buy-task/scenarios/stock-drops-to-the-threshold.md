---
kind: primary
routes:
  panel: Panel
steps:
- text: A part with Auto-create buy task has stock at or below Reorder at and no Buy task
  kind: condition
  unattended: true
  entities:
  - {entity: part, effect: reads, facts: [Stock, Reorder at, Auto-create buy task]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product adds a one-off Buy task on the appliance's device, due now with the status Low stock
  kind: product
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Schedule kind, Due date, Device]}
  - {entity: appliance, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Stock drops to the reorder threshold

## Trigger

A completion or an adjustment takes a part's stock to its reorder threshold.

## Outcome

One Buy task for the part is in the Shopping section.

## Edge cases

- A Buy task follows a rename of its part unless someone renamed the task.
