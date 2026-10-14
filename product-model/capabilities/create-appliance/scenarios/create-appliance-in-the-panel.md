---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Add appliance and enters the details
  kind: actor
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::new-appliance'}
- text: The Product creates the appliance with its own virtual device
  kind: product
  actor: admin
  entities:
  - {entity: appliance, effect: creates, to: Active, facts: [Name, Device, Icon, Manufacturer, Model, Serial number, Replacement cost, Notes, Custom fields, Tracked dates, Area, Parent appliance, Related devices]}
  contexts:
    panel: {place: 'panel::household::new-appliance'}
---

# Create an appliance in the panel

## Trigger

An admin presses Add appliance.

## Outcome

The appliance exists with its device page.
