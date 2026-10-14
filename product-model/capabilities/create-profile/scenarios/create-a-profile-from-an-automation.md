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
  - {entity: profile, effect: creates, facts: [Name, Include]}
  contexts:
    services: {place: services}
---

# Create a profile from an automation

## Trigger

An automation calls the set options action with a new profile.

## Outcome

The profile is saved.
