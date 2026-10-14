---
kind: primary
routes:
  card: Dashboard card
steps:
- text: The Household member selects the Note chip of a task
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Notes]}
  contexts:
    card: {place: dashboard-card}
- text: The Product opens the note in a read-only dialog
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Notes]}
  contexts:
    card: {place: dashboard-card}
---

# Read a task's note on the card

## Trigger

A household member selects the Note chip of a task on the card.

## Outcome

The note opens read-only, rendered as Markdown.
