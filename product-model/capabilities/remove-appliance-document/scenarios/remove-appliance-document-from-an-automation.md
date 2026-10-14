---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the remove asset document action
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product removes the document
  kind: product
  actor: automation
  entities:
  - {entity: appliance-document, effect: removes}
  contexts:
    services: {place: services}
---

# Remove an appliance document from an automation

## Trigger

An automation calls the remove asset document action.

## Outcome

The document is gone.
