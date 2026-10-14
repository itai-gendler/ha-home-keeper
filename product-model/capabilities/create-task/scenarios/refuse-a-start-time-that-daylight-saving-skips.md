---
kind: validation
routes:
  panel: Panel
steps:
- text: The Household member picks a start time inside the daylight-saving gap
  kind: actor
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The start time does not exist in the Home Assistant time zone
  kind: condition
  entities: []
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product refuses the task and asks for a different time
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::new-task'}
---

# Refuse a fixed start time that daylight saving skips

## Trigger

A household member picks a fixed start time in the hour the clocks skip.

## Outcome

No task is created and the form asks for a different time.
