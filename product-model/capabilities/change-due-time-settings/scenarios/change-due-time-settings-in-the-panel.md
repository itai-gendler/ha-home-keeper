---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin selects At a set time and sets 08:00
  kind: actor
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: reads, facts: [Due time]}
  contexts:
    panel: {place: 'panel::administration::settings'}
- text: The Product saves the change at once and applies it
  kind: product
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: changes, facts: [Due time]}
  contexts:
    panel: {place: 'panel::administration::settings'}
---

# Change the due time settings in the panel

## Trigger

An admin opens Settings.

## Outcome

Each repeating task that is due later is due at the set time on its date; a task that is due now stays due now.
