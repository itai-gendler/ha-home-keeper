---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin turns off Show on the companion's row
  kind: actor
  actor: admin
  entities:
  - {entity: companion, effect: reads, facts: [Panel tab]}
  contexts:
    panel: {place: 'panel::administration::companions'}
- text: The Product hides the tab
  kind: product
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: changes, facts: [Hidden panel tabs]}
  contexts:
    panel: {place: 'panel::administration::companions'}
---

# Turn off Show

## Trigger

An admin turns off the Show switch of a companion's tab.

## Outcome

The tab is gone from the tab bar.
