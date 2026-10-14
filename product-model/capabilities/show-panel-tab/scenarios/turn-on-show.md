---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin turns on Show on the companion's row
  kind: actor
  actor: admin
  entities:
  - {entity: companion, effect: reads, facts: [Panel tab]}
  contexts:
    panel: {place: 'panel::administration::companions'}
- text: The Product shows the tab
  kind: product
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: changes, facts: [Hidden panel tabs]}
  contexts:
    panel: {place: 'panel::administration::companions'}
---

# Turn on Show

## Trigger

An admin turns on the Show switch of a hidden tab.

## Outcome

The tab is back.
