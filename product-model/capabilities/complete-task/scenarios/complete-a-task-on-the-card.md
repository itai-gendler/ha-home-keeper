---
kind: primary
routes:
  card: Dashboard card
steps:
- text: The Household member presses Done on a task row
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    card: {place: dashboard-card}
- text: The Product records the completion and reschedules the task
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    card: {place: dashboard-card}
---

# Complete a task on the dashboard card

## Trigger

A household member presses Done on the card.

## Outcome

The task is completed and the card updates.

## Edge cases

- A task that requires details sends the household member to its page in the panel.
- A scan-only task explains that a scan completes it.
