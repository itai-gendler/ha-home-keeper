---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin selects the matching presets and presses Add
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product saves each preset as a declarative companion with its defaults
  kind: product
  actor: admin
  entities:
  - {entity: declarative-companion, effect: creates, to: 'On', facts: [Name, Target integration, Trigger mode, Trigger condition, Auto-clear]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Add suggested presets from the Tasks tab

## Trigger

An admin sees the Presets you can use dialog.

## Outcome

The selected presets are saved with their default settings.

## Edge cases

- A preset that matches more than 50 entities is offered on the card with Set up instead.
