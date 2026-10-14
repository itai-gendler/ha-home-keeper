---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin sets One-off retention and leaves the box
  kind: actor
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: reads, facts: [One-off retention]}
  contexts:
    panel: {place: 'panel::administration::settings'}
- text: The Product saves the change at once and applies it
  kind: product
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: changes, facts: [One-off retention]}
  contexts:
    panel: {place: 'panel::administration::settings'}
---

# Change the general settings in the panel

## Trigger

An admin opens Settings.

## Outcome

Completed one-off tasks are kept for the new number of days.
