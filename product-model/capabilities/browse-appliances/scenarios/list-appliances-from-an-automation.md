---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the list assets action
  kind: actor
  actor: automation
  entities:
  - {entity: appliance, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product answers with every appliance, its parts and documents
  kind: product
  actor: automation
  entities:
  - {entity: appliance, effect: reads, facts: [Name, Manufacturer, Model, Serial number, Replacement cost]}
  - {entity: part, effect: reads, facts: [Name, Stock]}
  - {entity: appliance-document, effect: reads, facts: [Name]}
  contexts:
    services: {place: services}
---

# List appliances from an automation

## Trigger

An automation calls the list assets action.

## Outcome

It receives every appliance with its full record.
