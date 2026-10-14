---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin selects an existing device
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::new-appliance'}
- text: The Product prefills the maker, model and serial number from the device registry and creates the appliance on that device
  kind: product
  actor: admin
  entities:
  - {entity: appliance, effect: creates, to: Active, facts: [Name, Device, Manufacturer, Model, Serial number]}
  contexts:
    panel: {place: 'panel::household::new-appliance'}
---

# Add an appliance on an existing device

## Trigger

An admin selects an existing Home Assistant device.

## Outcome

The device carries the appliance record; Home Keeper does not own the device.
