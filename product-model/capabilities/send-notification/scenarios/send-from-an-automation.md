---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the notify action with a notification or a profile, and optional targets, status and when empty
  kind: actor
  actor: automation
  entities:
  - {entity: profile, effect: reads, facts: []}
  - {entity: notification, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product sends the matching tasks, or All caught up only when the call asks for it
  kind: product
  actor: automation
  entities:
  - {entity: profile, effect: reads, facts: [Include]}
  - {entity: task, effect: reads, facts: [Name, Due date]}
  contexts:
    services: {place: services}
---

# Send from an automation

## Trigger

An automation calls the notify action.

## Outcome

The destinations receive the due tasks, or nothing when none matches.

## Edge cases

- A target that is not a companion-app device or persistent notification fails the call.
