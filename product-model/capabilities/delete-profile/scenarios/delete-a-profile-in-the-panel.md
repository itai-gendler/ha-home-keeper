---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin deletes the profile
  kind: actor
  actor: admin
  entities:
  - {entity: profile, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::administration::profiles'}
- text: The Product removes the profile
  kind: product
  actor: admin
  entities:
  - {entity: profile, effect: removes}
  contexts:
    panel: {place: 'panel::administration::profiles'}
---

# Delete a profile in the panel

## Trigger

An admin deletes a profile no notification uses.

## Outcome

The profile and its count sensor are gone.
