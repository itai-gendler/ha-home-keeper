---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin selects a to-do list and Product only
  kind: actor
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: reads, facts: [Shopping list, Line text on list]}
  contexts:
    panel: {place: 'panel::administration::settings'}
- text: The Product saves the change at once and applies it
  kind: product
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: changes, facts: [Shopping list, Line text on list]}
  contexts:
    panel: {place: 'panel::administration::settings'}
---

# Change the shopping list settings in the panel

## Trigger

An admin opens Settings.

## Outcome

Buy tasks are synced to the chosen list with the chosen line text; clearing the list turns the sync off.
