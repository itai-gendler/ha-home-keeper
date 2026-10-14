---
kind: primary
routes:
  card: Dashboard card
steps:
- text: The Household member presses Skip
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: skip, effect: reads, facts: []}
  contexts:
    card: {place: dashboard-card}
- text: The Product records the skip and advances the task
  kind: product
  actor: household-member
  entities:
  - {entity: skip, effect: creates, facts: [Skipped at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    card: {place: dashboard-card}
---

# Skip a task on the card

## Trigger

A household member presses Skip on a card row.

## Outcome

The task moves to its next occurrence.
