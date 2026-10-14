---
kind: alternative
routes:
  services: Services
steps:
- text: The Companion calls the update managed asset action
  kind: actor
  actor: companion
  entities: []
  contexts:
    services: {place: services}
- text: The Product updates the name and the parts it owns and keeps every stock field
  kind: product
  actor: companion
  entities:
  - {entity: appliance, effect: changes, facts: [Name]}
  - {entity: part, effect: changes, facts: [Name, Notes]}
  contexts:
    services: {place: services}
---

# A companion keeps its appliance current

## Trigger

A companion's list of parts changes.

## Outcome

The appliance has the owner's name and parts; the stock numbers stay the household's.
