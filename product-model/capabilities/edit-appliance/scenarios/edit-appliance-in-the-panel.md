---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Edit, changes the details and presses Save
  kind: actor
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product saves the appliance and its device page
  kind: product
  actor: admin
  entities:
  - {entity: appliance, effect: changes, facts: [Name, Manufacturer, Model, Serial number, Notes, Custom fields, Tracked dates, Parent appliance, Related devices]}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Edit an appliance in the panel

## Trigger

An admin presses Edit on an appliance.

## Outcome

The appliance has the new details.
