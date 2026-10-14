---
kind: primary
routes:
  notifications: Mobile notifications
steps:
- text: The Household member presses Mark done on the notification
  kind: actor
  actor: household-member
  entities:
  - {entity: task, effect: reads, facts: [Name]}
  - {entity: notification, effect: reads, facts: []}
  contexts:
    notifications: {place: mobile-notifications}
- text: The notification is still current for the task
  kind: condition
  entities:
  - {entity: task, effect: reads, facts: [Due date]}
  - {entity: notification, effect: reads, facts: []}
  contexts:
    notifications: {place: mobile-notifications}
- text: The Product records the completion and reschedules the task
  kind: product
  actor: household-member
  entities:
  - {entity: completion, effect: creates, facts: [Completed at]}
  - {entity: task, effect: changes, from: Scheduled, to: Scheduled, facts: [Due date, Last completed]}
  contexts:
    notifications: {place: mobile-notifications}
- text: For a walk, the Product sends the next due task to the same destinations, or All caught up
  kind: product
  actor: household-member
  entities:
  - {entity: notification, effect: reads, facts: [Style, Send to]}
  - {entity: task, effect: reads, facts: [Name, Due date]}
  contexts:
    notifications: {place: mobile-notifications}
---

# Complete a task from a notification

## Trigger

A household member presses Mark done on a notification.

## Outcome

The task is completed; a walk sends the next due task.

## Edge cases

- A button on a notification that is no longer current does nothing.
