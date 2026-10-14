---
kind: validation
routes:
  services: Services
steps:
- text: The Household member runs a script that calls the add asset action
  kind: actor
  actor: household-member
  entities: []
  contexts:
    services: {place: services}
- text: The caller lacks Home Assistant administrator rights
  kind: condition
  entities: []
  contexts:
    services: {place: services}
- text: The Product refuses the call as unauthorized
  kind: product
  actor: household-member
  entities: []
  contexts:
    services: {place: services}
---

# Refuse to create an appliance for a household member

## Trigger

A household member runs a script that calls the add asset action.

## Outcome

No appliance is created.
