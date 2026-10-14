---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Not now on the Presets for your home card
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product keeps those presets as put aside for this person and hides the card
  kind: product
  actor: admin
  entities:
  - {entity: home-assistant-user, effect: changes, facts: [Hidden preset suggestions]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Press Not now

## Trigger

An admin sees the Presets you can use dialog or the Presets for your home card.

## Outcome

The card is hidden and those presets are not suggested again.
