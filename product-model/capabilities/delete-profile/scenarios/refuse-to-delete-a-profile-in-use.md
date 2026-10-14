---
kind: validation
routes:
  panel: Panel
steps:
- text: The Admin deletes a profile
  kind: actor
  actor: admin
  entities:
  - {entity: profile, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::administration::profiles'}
- text: A notification uses the profile
  kind: condition
  entities:
  - {entity: notification, effect: reads, facts: [Profile]}
  - {entity: profile, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::administration::profiles'}
- text: The Product refuses the save and says to point those notifications at another profile first
  kind: product
  actor: admin
  entities:
  - {entity: profile, effect: reads, facts: []}
  - {entity: notification, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::administration::profiles'}
---

# Refuse to delete a profile a notification uses

## Trigger

An admin deletes a profile that a notification uses.

## Outcome

The profile stays.
