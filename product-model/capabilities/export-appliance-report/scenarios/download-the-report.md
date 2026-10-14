---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Export appliance report
  kind: actor
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
- text: The Product writes the CSV with a row for each appliance and a total
  kind: product
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: [Name, Manufacturer, Model, Replacement cost, Custom fields]}
  - {entity: part, effect: reads, facts: [Stock, Cost]}
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
---

# Download the appliance report

## Trigger

An admin presses the appliance report.

## Outcome

The CSV file is saved.
