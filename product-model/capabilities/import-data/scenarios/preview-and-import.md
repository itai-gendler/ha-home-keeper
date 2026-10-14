---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin pastes the file and presses Preview
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
- text: The Product checks every section and reports the new and updated records and the problems, writing nothing
  kind: product
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
- text: The Admin presses Import
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
- text: The Product creates or updates each record and adds its history
  kind: product
  actor: admin
  entities:
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Schedule kind, External id]}
  - {entity: completion, effect: creates, facts: [Completed at, Note, Cost], with: task}
  - {entity: appliance, effect: creates, to: Active, facts: [Name, Manufacturer, Model, External id]}
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
---

# Preview and import a file

## Trigger

An admin pastes a YAML file or chooses a bundle.

## Outcome

The records in the file are created or updated.

## Edge cases

- Import stays off until a preview of that exact input comes back clean.
- A name that matches 2 records is an error that names both.
- A companion that fails while it writes leaves the Home Keeper records written and the report partial.
