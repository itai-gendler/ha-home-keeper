---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the add asset document action with a link
  kind: actor
  actor: automation
  entities: []
  contexts:
    services: {place: services}
- text: The Product adds the link document
  kind: product
  actor: automation
  entities:
  - {entity: appliance-document, effect: creates, facts: [Name, Link]}
  contexts:
    services: {place: services}
---

# Add an appliance document from an automation

## Trigger

An automation calls the add asset document action.

## Outcome

The document is on the appliance.
