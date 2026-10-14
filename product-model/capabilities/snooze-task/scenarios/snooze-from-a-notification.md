---
kind: primary
routes:
  notifications: Mobile notifications
steps:
- text: The Household member presses Snooze
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    notifications: {place: mobile-notifications}
- text: The Product snoozes the task by its own snooze length, else by the notification's snooze duration
  kind: product
  actor: household-member
  entities:
  - {entity: notification, effect: reads, facts: [Snooze duration]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date]}
  contexts:
    notifications: {place: mobile-notifications}
---

# Snooze a task from a notification

## Trigger

A household member presses Snooze on a notification.

## Outcome

The task is due later by the task's snooze length or the notification's duration.
