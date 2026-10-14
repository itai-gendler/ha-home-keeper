---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin changes the labels and saves
  kind: actor
  actor: admin
  entities:
  - {entity: declarative-companion, effect: reads, facts: [Task labels]}
  contexts:
    panel: {place: 'panel::administration::declarative-companion'}
- text: The Product saves it and adds and removes those labels on its tasks
  kind: product
  actor: admin
  entities:
  - {entity: declarative-companion, effect: changes, facts: [Task labels]}
  - {entity: task, effect: changes, facts: [Labels]}
  contexts:
    panel: {place: 'panel::administration::declarative-companion'}
---

# Change the task labels

## Trigger

An admin presses Edit on a declarative companion.

## Outcome

Its tasks carry the new labels; labels added to one task stay.

## Edge cases

- Reset to preset puts back the preset's sections and keeps the name, description and exclusions.
