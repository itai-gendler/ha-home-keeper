---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Dismiss
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::administration::companions'}
- text: The Product adds the integration to the dismissed list
  kind: product
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: changes, facts: [Dismissed companions]}
  contexts:
    panel: {place: 'panel::administration::companions'}
---

# Press Dismiss

## Trigger

An admin presses Dismiss on a suggested companion.

## Outcome

The suggestion is gone from the list.
