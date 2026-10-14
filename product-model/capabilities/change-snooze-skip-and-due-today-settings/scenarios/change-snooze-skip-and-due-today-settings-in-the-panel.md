---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin turns off one of the three switches
  kind: actor
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: reads, facts: [Snooze on, Skip on, Due today on]}
  contexts:
    panel: {place: 'panel::administration::settings'}
- text: The Product saves the change at once and applies it
  kind: product
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: changes, facts: [Snooze on, Skip on, Due today on]}
  contexts:
    panel: {place: 'panel::administration::settings'}
---

# Change the snooze, skip and due today settings in the panel

## Trigger

An admin opens Settings.

## Outcome

The turned-off action is gone from the panel, the card and the notification buttons.
