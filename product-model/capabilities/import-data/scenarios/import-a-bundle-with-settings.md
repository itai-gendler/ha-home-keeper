---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin chooses a bundle, selects Also import the settings, previews and imports
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
- text: The Product updates or adds the profiles and notifications by id, then by name, and adds files records do not have
  kind: product
  actor: admin
  entities:
  - {entity: profile, effect: creates, facts: [Name, Include]}
  - {entity: notification, effect: creates, facts: [Name, Profile], with: profile}
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
---

# Import a bundle with its settings

## Trigger

An admin selects Also import the settings from the bundle.

## Outcome

Profiles and notifications are updated or added; none is deleted.

## Edge cases

- A notify target or to-do list this Home Assistant does not have gives a warning.
