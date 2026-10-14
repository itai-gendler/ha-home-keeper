---
kind: edge
result: achieved
routes:
  panel: Panel
steps:
- text: The Household member fills the New task form, adds photos and presses Create
  kind: actor
  actor: household-member
  capability: create-task
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product creates the task and a photo fails to upload
  kind: product
  actor: household-member
  capability: create-task
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Schedule kind, Due date]}
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product opens the task page with a message counting the photos that did not upload
  kind: product
  actor: household-member
  capability: create-task
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Household member selects Add photo and picks the image again
  kind: actor
  actor: household-member
  capability: add-task-photo
  entities: []
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product adds the photo to the task
  kind: product
  actor: household-member
  capability: add-task-photo
  entities:
  - {entity: task-photo, effect: creates, facts: [Image, Cover]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Add photos again after a failed upload

## Trigger

A household member creates a task with photos and one photo does not upload.

## Outcome

The task holds every photo, and the household member stayed on its page to finish.
