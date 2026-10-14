---
kind: primary
routes:
  notifications: Mobile notifications
steps:
- text: The Household member presses Skip
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: skip, effect: reads, facts: []}
  contexts:
    notifications: {place: mobile-notifications}
- text: The Product records the skip and advances the task
  kind: product
  actor: household-member
  entities:
  - {entity: skip, effect: creates, facts: [Skipped at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    notifications: {place: mobile-notifications}
---

# Skip a task from a notification

## Trigger

A household member presses Skip on a notification.

## Outcome

The task moves to its next occurrence.
