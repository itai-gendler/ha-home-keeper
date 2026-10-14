---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member picks Tiles in the Layout menu
  kind: actor
  actor: household-member
  entities:
  - {entity: home-assistant-user, effect: reads, facts: [Task list layout]}
  contexts:
    panel: {place: 'panel::household::task-list'}
- text: The Product keeps the layout for the person and redraws the list
  kind: product
  actor: household-member
  entities:
  - {entity: home-assistant-user, effect: changes, facts: [Task list layout]}
  contexts:
    panel: {place: 'panel::household::task-list'}
---

# Pick a layout

## Trigger

A household member opens the Layout menu.

## Outcome

The Tasks tab shows the chosen layout on every device of that person.
