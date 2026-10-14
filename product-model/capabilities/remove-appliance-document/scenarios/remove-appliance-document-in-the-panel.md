---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses remove on a document and confirms
  kind: actor
  actor: admin
  entities:
  - {entity: appliance-document, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product removes the document and deletes its file
  kind: product
  actor: admin
  entities:
  - {entity: appliance-document, effect: removes}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Remove an appliance document in the panel

## Trigger

An admin removes a document.

## Outcome

The document is gone.
