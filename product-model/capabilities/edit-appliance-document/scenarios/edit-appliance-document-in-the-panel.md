---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin presses Edit on a document and changes its name
  kind: actor
  actor: admin
  entities:
  - {entity: appliance-document, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product saves the document
  kind: product
  actor: admin
  entities:
  - {entity: appliance-document, effect: changes, facts: [Name, Link]}
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Edit an appliance document in the panel

## Trigger

An admin presses Edit on a document.

## Outcome

The document has the new name or link.
