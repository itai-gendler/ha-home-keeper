---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the set options action without the profile
  kind: actor
  actor: automation
  entities:
  - {entity: profile, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product removes the profile
  kind: product
  actor: automation
  entities:
  - {entity: profile, effect: removes}
  contexts:
    services: {place: services}
---

# Delete a profile from an automation

## Trigger

An automation calls the set options action without the profile.

## Outcome

The profile is gone.
