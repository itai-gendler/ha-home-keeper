---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member selects delete on the photo and confirms
  kind: actor
  actor: household-member
  entities:
  - {entity: task-photo, effect: reads, facts: [Image]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product deletes the photo and its file
  kind: product
  actor: household-member
  entities:
  - {entity: task-photo, effect: removes}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Remove a photo

## Trigger

A household member selects delete on a photo.

## Outcome

The photo and its file are gone.
