---
kind: alternative
routes:
  panel: Panel
steps:
- text: The Admin switches Due time back from a set time
  kind: actor
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: reads, facts: [Due time]}
  contexts:
    panel: {place: 'panel::administration::settings'}
- text: The Product saves the choice and leaves the due dates as they are
  kind: product
  actor: admin
  entities:
  - {entity: home-keeper-settings, effect: changes, facts: [Due time]}
  contexts:
    panel: {place: 'panel::administration::settings'}
---

# Return to the time of completion

## Trigger

An admin selects At the time of completion again.

## Outcome

Tasks keep the set time until their next completion.
