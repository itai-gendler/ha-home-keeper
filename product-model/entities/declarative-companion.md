---
domain: companions
relations:
- entity: task
  verb: opens
  cardinality: one-to-many
references:
- kind: doc
  role: intent
  target: docs/guide/views/settings.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/declarative_companions.py
---

# Declarative companion

A saved rule, from a preset or written by an admin, that opens a managed task for each Home Assistant entity it matches while the entity's condition holds.

## Information kept

- **Name** — its name
- **Description** — what it does
- **Target integration** — the integration whose entities it watches
- **Entity filters** — domain, device class, entity id pattern, devices, areas and labels
- **Entity keys** — the integration's entity keys it matches, each with an optional task name
- **Exclusions** — entities, devices, areas and labels it leaves out
- **Trigger mode** — usage, threshold, state, availability or template
- **Trigger condition** — the limit, state, hold or template
- **Task name template** — the template for each task's name
- **Task notes template** — the template for each task's notes
- **Task labels** — labels put on each task
- **Auto-clear** — whether a task completes itself when the condition recovers

## States

### On

It opens and clears its tasks.

### Off

Its tasks stay and stop until it is on again.
