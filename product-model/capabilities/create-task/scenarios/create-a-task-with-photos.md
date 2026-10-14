---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Household member fills the form, adds photos and stars one as the cover
  kind: actor
  actor: household-member
  entities: []
  contexts:
    panel: {place: 'panel::household::new-task'}
- text: The Product creates the task, then uploads each photo
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Notes, Schedule kind, Interval, Due date, Device, Area, Labels, On completion]}
  - {entity: task-photo, effect: creates, facts: [Image, Cover], with: task}
  contexts:
    panel: {place: 'panel::household::new-task'}
---

# Create a task with photos

## Trigger

A household member adds photos in the New task form.

## Outcome

The task exists with its photos.

## Edge cases

- When a photo fails to upload, the task stays, the task page opens and a message counts the photos that did not upload.
