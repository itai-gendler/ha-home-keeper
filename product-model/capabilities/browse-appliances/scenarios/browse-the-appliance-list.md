---
kind: primary
routes:
  panel: Panel
steps:
- text: The Household member opens the Appliances tab
  kind: actor
  actor: household-member
  entities:
  - {entity: appliance, effect: reads, facts: []}
  contexts:
    panel: {place: 'panel::household::appliance-list'}
- text: The Product lists the active appliances with their icon, make, model and area, and a View only note for a household member
  kind: product
  actor: household-member
  entities:
  - {entity: appliance, effect: reads, facts: [Name, Icon, Manufacturer, Model, Area, Managed by]}
  contexts:
    panel: {place: 'panel::household::appliance-list'}
- text: The Household member switches to Archived and to the tree view
  kind: actor
  actor: household-member
  entities:
  - {entity: appliance, effect: reads, facts: [Parent appliance]}
  contexts:
    panel: {place: 'panel::household::appliance-list'}
- text: The Product shows the archived appliances with children under their parents
  kind: product
  actor: household-member
  entities:
  - {entity: appliance, effect: reads, facts: [Name, Parent appliance]}
  contexts:
    panel: {place: 'panel::household::appliance-list'}
---

# Browse the appliance list

## Trigger

A household member opens the Appliances tab.

## Outcome

The household member sees the appliances; the tab says it is view only.
