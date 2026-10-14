---
kind: primary
routes:
  notifications: Mobile notifications
steps:
- text: A task in the profile becomes overdue while Send when overdue is on
  kind: condition
  unattended: true
  entities:
  - {entity: notification, effect: reads, facts: [Send when overdue, Profile]}
  - {entity: task, effect: reads, facts: [Due date]}
  - {entity: profile, effect: reads, facts: []}
  contexts:
    notifications: {place: mobile-notifications}
- text: The Product sends the first due task, or the digest, with the configured buttons, channel, urgency, icon and color, in the Home Assistant language
  kind: product
  entities:
  - {entity: notification, effect: reads, facts: [Send to, Buttons, Style, Notification channel, Urgency, Notification icon, Accent color]}
  - {entity: task, effect: reads, facts: [Name, Due date]}
  contexts:
    notifications: {place: mobile-notifications}
---

# Send when a task becomes overdue

## Trigger

A task in a notification's profile becomes overdue.

## Outcome

The phones receive the notification with its buttons.

## Edge cases

- A task a snooze or completion moves straight into due soon does not send for due soon.
- A synced problem task offers Snooze instead of Mark done and Skip.
