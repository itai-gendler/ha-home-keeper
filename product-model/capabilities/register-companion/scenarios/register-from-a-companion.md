---
kind: primary
routes:
  services: Services
steps:
- text: The Companion calls the register companion action with its name and configure link
  kind: actor
  actor: companion
  entities: []
  contexts:
    services: {place: services}
- text: The Product keeps the registration
  kind: product
  actor: companion
  entities:
  - {entity: companion, effect: changes, facts: [Name, Integration, Configure link]}
  contexts:
    services: {place: services}
---

# A companion registers

## Trigger

A companion starts, or Home Keeper asks companions to register again.

## Outcome

The companion is listed as connected.

## Edge cases

- A registration never adds a panel tab.
