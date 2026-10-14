---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the set options action with the profiles list
  kind: actor
  actor: automation
  entities:
  - {entity: profile, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product saves the profile
  kind: product
  actor: automation
  entities:
  - {entity: profile, effect: changes, facts: [Include, Labels]}
  contexts:
    services: {place: services}
---

# Edit a profile from an automation

## Trigger

An automation calls the set options action with changed profiles.

## Outcome

The profile has the new filters.
