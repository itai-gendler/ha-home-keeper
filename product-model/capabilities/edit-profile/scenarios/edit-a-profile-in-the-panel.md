---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin expands the profile and changes its filters
  kind: actor
  actor: admin
  entities:
  - {entity: profile, effect: reads, facts: [Name, Include, Labels, Areas, Devices, Companions, Exclude labels, Exclude areas, Exclude devices, Exclude companions, Exclude shopping]}
  contexts:
    panel: {place: 'panel::administration::profiles'}
- text: The Product saves the profile
  kind: product
  actor: admin
  entities:
  - {entity: profile, effect: changes, facts: [Name, Include, Labels, Areas, Devices, Companions, Exclude labels, Exclude areas, Exclude devices, Exclude companions, Exclude shopping]}
  contexts:
    panel: {place: 'panel::administration::profiles'}
---

# Edit a profile in the panel

## Trigger

An admin expands a profile.

## Outcome

The profile selects tasks by the new filters everywhere it is used.

## Edge cases

- A renamed profile keeps the entity id of its count sensor.
