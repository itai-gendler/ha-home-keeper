---
kind: primary
routes:
  services: Services
steps:
- text: The Automation calls the set task meter action, with or without a baseline
  kind: actor
  actor: automation
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    services: {place: services}
- text: The Product sets the baseline, the current reading when none is given
  kind: product
  actor: automation
  entities:
  - {entity: task, effect: changes, facts: [Meter baseline]}
  contexts:
    services: {place: services}
---

# Re-anchor at the current reading

## Trigger

An automation calls the set task meter action.

## Outcome

The usage counts from the new baseline.

## Edge cases

- A task that is not a usage task is refused.
- No baseline and no current reading is refused.
