---
kind: primary
routes:
  card: Dashboard card
steps:
- text: The Household member selects Add photo in the card form
  kind: actor
  actor: household-member
  entities: []
  contexts:
    card: {place: dashboard-card}
- text: The Product uploads the photo to the task
  kind: product
  actor: household-member
  entities:
  - {entity: task-photo, effect: creates, facts: [Image, Cover]}
  - {entity: task, effect: reads, facts: []}
  contexts:
    card: {place: dashboard-card}
---

# Add a photo on the card

## Trigger

A household member adds a photo in the card's New task form.

## Outcome

The photo is on the new task.
