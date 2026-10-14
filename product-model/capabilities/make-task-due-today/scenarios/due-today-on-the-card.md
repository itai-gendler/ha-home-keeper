---
kind: primary
routes:
  card: Dashboard card
steps:
- text: The Household member presses Due today
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Due date]}
  contexts:
    card: {place: dashboard-card}
- text: The Product moves the due date to today
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    card: {place: dashboard-card}
---

# Press Due today on the card

## Trigger

A household member presses Due today on a card row.

## Outcome

The task is due today.
