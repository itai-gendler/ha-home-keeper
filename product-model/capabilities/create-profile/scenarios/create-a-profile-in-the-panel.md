---
kind: primary
routes:
  panel: Panel
steps:
- text: The Admin adds a profile, names it and sets Include and the filters
  kind: actor
  actor: admin
  entities:
  - {entity: profile, effect: reads, facts: [Name]}
  contexts:
    panel: {place: 'panel::administration::profiles'}
- text: The Product saves the profile
  kind: product
  actor: admin
  entities:
  - {entity: profile, effect: creates, facts: [Name, Include, Labels, Areas, Devices, Companions, Exclude labels, Exclude areas, Exclude devices, Exclude companions, Exclude shopping]}
  contexts:
    panel: {place: 'panel::administration::profiles'}
---

# Create a profile in the panel

## Trigger

An admin adds a profile in Settings → Profiles.

## Outcome

The profile is saved and can be picked everywhere.
