---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member presses Done
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [On completion, Required completion fields]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Household member fills Completed at, a note, a cost, a photo, who did it and the reading
  kind: actor
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product records the completion with its details and moves the due date from the completion time
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at, Note, Cost, Photo, Who, Reading]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed, Meter baseline]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Complete a task with details

## Trigger

A household member completes a task that asks for or requires details.

## Outcome

The completion carries the note, cost, photo, person and reading.

## Edge cases

- Require details keeps Done off until the required fields are filled.
- Ask for details offers Skip details, which completes with none.
- A completion older than the latest one only adds to the history.
