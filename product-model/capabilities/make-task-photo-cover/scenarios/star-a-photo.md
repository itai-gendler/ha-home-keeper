---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member selects the star on a photo
  kind: actor
  actor: household-member
  entities:
  - {entity: task-photo, effect: reads, facts: [Image, Cover]}
  contexts:
    panel: {place: 'panel::household::task'}
- text: The Product makes it the first photo
  kind: product
  actor: household-member
  entities:
  - {entity: task-photo, effect: changes, facts: [Cover]}
  contexts:
    panel: {place: 'panel::household::task'}
---

# Star a photo

## Trigger

A household member selects the star on a photo.

## Outcome

That photo is the cover.
