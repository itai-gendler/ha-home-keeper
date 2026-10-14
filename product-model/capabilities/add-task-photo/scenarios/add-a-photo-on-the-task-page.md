---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member selects Add photo and picks an image
  kind: actor
  actor: household-member
  entities:
  - {entity: task-photo, effect: reads, facts: [Image]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product stores the image with a small copy for lists
  kind: product
  actor: household-member
  entities:
  - {entity: task-photo, effect: creates, facts: [Image, Cover]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Add a photo on the task page

## Trigger

A household member selects Add photo on the task's Schedule tab.

## Outcome

The photo is on the task.

## Edge cases

- A file that is not a PNG, JPEG, WebP or GIF image, or larger than 25 MB, is refused.
- A seventh photo is refused.
