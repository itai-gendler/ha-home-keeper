---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Add part and fills the part
  kind: actor
  actor: admin
  entities:
  - {entity: appliance, effect: reads, facts: [Name]}
  - {entity: part, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Admin presses Save
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product adds the part and, for a wear item with an interval, a task on the appliance's device
  kind: product
  actor: admin
  entities:
  - {entity: part, effect: creates, facts: [Name, Part number, Vendor, Cost, Notes, Kind, Replacement interval, Action, Stock, Reorder at, Auto-create buy task, Product URL, NFC tag, Require tag scan]}
  - {entity: task, effect: creates, to: Scheduled, facts: [Name, Schedule kind, Interval, Due date, Device, Managed by], with: part}
  - {entity: appliance, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Add a part in the panel

## Trigger

An admin presses Add part on an appliance.

## Outcome

The part is on the appliance.
