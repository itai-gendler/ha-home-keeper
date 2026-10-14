---
kind: primary
routes:
  card: Dashboard card
steps:
- text: The Household member presses Snooze and picks a duration
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Due date]}
  contexts:
    card: {place: dashboard-card}
- text: The Product moves the due date later
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    card: {place: dashboard-card}
---

# Snooze a task on the card

## Trigger

A household member presses Snooze on a card row.

## Outcome

The task is due later.
