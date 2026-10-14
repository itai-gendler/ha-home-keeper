---
kind: alternative
routes:
  notifications: Mobile notifications
steps:
- text: The Household member presses Open
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    notifications: {place: mobile-notifications}
- text: The Product opens the task's page in Home Keeper
  kind: product
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    notifications: {place: mobile-notifications}
---

# Open a task from a notification

## Trigger

A household member presses Open on a notification.

## Outcome

The task's page opens in the panel.
