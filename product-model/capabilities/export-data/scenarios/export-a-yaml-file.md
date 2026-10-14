---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin clears the sources not wanted and presses Export data (.yaml)
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
- text: The Product writes every task and appliance with its history, without photos or files and without appliances a companion manages
  kind: product
  actor: admin
  entities:
  - {entity: task, effect: reads, facts: [Name, Notes, Schedule kind, Interval, External id]}
  - {entity: completion, effect: reads, facts: [Completed at, Note, Cost]}
  - {entity: appliance, effect: reads, facts: [Name, Manufacturer, Model, Serial number, External id]}
  - {entity: companion, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
---

# Export a YAML file

## Trigger

An admin presses Export data.

## Outcome

The file holds the checked sources; the card names them.

## Edge cases

- A companion whose export fails is named on the card.
