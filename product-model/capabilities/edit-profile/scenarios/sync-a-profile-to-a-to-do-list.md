---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin selects a to-do list and sets Two-way sync and Treat removed items as completed
  kind: actor
  actor: admin
  entities:
  - {entity: profile, effect: reads, facts: [To-do list]}
  contexts:
    panel: {place: 'panel::administration::profiles'}
- text: The Product saves the sync
  kind: product
  actor: admin
  entities:
  - {entity: profile, effect: changes, facts: [To-do list, Two-way sync, Treat removed items as completed]}
  contexts:
    panel: {place: 'panel::administration::profiles'}
---

# Sync a profile to a to-do list

## Trigger

An admin selects a list in Sync to a to-do list.

## Outcome

The profile's tasks are added to the list as they come into its tier.

## Edge cases

- Clearing the list stops the sync and removes the profile's open items from it.
