---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin opens Manuals & documents and presses Upload file
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product stores the file under the configuration and adds the document
  kind: product
  actor: admin
  entities:
  - {entity: appliance-document, effect: creates, facts: [Name, File]}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Add an appliance document in the panel

## Trigger

An admin uploads a manual.

## Outcome

The document is on the appliance.
