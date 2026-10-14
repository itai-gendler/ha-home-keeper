---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the update asset document action
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product saves the document
  kind: product
  actor: automation
  entities:
  - {entity: appliance-document, effect: changes, facts: [Name, Link]}
  contexts:
    services: {place: services}
---

# Edit an appliance document from an automation

## Trigger

An automation calls the update asset document action.

## Outcome

The document has the new name or link.
